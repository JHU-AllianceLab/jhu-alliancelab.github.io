---
layout: page
title: "Guess 2/3 of the Average"
permalink: /teaching/HCR/game/
show_sidebar: false
hide_footer: false
hero_height: is-small
---

<div class="game-wrap">
  <p class="game-rules">
    Guess an integer in [0, 100] that is closest to <span class="game-accent">2/3 of the average</span> of all players' answers.
    <span class="game-rules-sub">Everyone whose number is closest wins.</span>
  </p>

  <div id="game-app" class="game-card">
    <p class="game-muted">Loading…</p>
  </div>

  <div id="game-admin" class="game-card game-admin" hidden></div>
</div>

<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.14.1/firebase-app.js";
  import { getAuth, signInAnonymously, signInWithEmailAndPassword, signOut, onAuthStateChanged }
    from "https://www.gstatic.com/firebasejs/10.14.1/firebase-auth.js";
  import { getFirestore, doc, getDoc, setDoc, onSnapshot, collection, getDocs, serverTimestamp }
    from "https://www.gstatic.com/firebasejs/10.14.1/firebase-firestore.js";

  const app = initializeApp({
    apiKey: "AIzaSyCMZP-M2X15w_Dz7z4br4kS1S1h0v4PHCg",
    authDomain: "jhu-hcr-collaboration-game.firebaseapp.com",
    projectId: "jhu-hcr-collaboration-game",
    storageBucket: "jhu-hcr-collaboration-game.firebasestorage.app",
    messagingSenderId: "831062949935",
    appId: "1:831062949935:web:4d627ef7fa835ce51ec6da"
  });
  const auth = getAuth(app);
  const db = getFirestore(app);

  const ADMIN_UID = "L39Yo1Ckeofsu6pOZImFCFP8CeT2";
  const instructorMode = new URLSearchParams(location.search).has("instructor");
  const stateRef = doc(db, "game", "state");

  const appEl = document.getElementById("game-app");
  const adminEl = document.getElementById("game-admin");

  const esc = s => String(s).replace(/[&<>"']/g, c => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c]));
  const fmt = x => Number(x).toFixed(2);

  let user = null;
  let state = null;
  const myGuessByRound = {};   // roundId -> {name, guess} | null
  let unsubGuesses = null;
  let lastStudentKey = null;   // skip redraws that would wipe what a student is typing

  // ---------- Results (shared by students and instructor) ----------
  function resultsHtml(s) {
    const nums = s.winningGuesses.join(" and ");
    const names = s.winners.map(w => esc(w.name)).join(", ");
    return `
      <div class="game-results">
        <div class="game-stat"><span>Players</span><strong>${s.count}</strong></div>
        <div class="game-stat"><span>Average</span><strong>${fmt(s.average)}</strong></div>
        <div class="game-stat"><span>2/3 of average</span><strong>${fmt(s.target)}</strong></div>
        <div class="game-stat game-stat--win"><span>Winning number${s.winningGuesses.length > 1 ? "s" : ""}</span><strong>${nums}</strong></div>
      </div>
      <p class="game-winners">🏆 Winner${s.winners.length > 1 ? "s" : ""}: <strong>${names}</strong></p>`;
  }

  // ---------- Student view ----------
  async function renderStudent() {
    if (!state || !state.roundId) {
      lastStudentKey = null;
      appEl.innerHTML = `<p class="game-muted">No game is open right now. Please wait for your instructor to start a round.</p>`;
      return;
    }
    const roundId = state.roundId;
    if (!(roundId in myGuessByRound)) {
      const snap = await getDoc(doc(db, "rounds", roundId, "guesses", user.uid));
      myGuessByRound[roundId] = snap.exists() ? snap.data() : null;
    }
    const mine = myGuessByRound[roundId];
    const key = `${roundId}|${state.status}|${mine ? mine.guess : ""}|${state.finalizedAt ? "f" : ""}`;
    if (key === lastStudentKey) return;
    lastStudentKey = key;

    if (state.status === "final") {
      let verdict;
      if (!mine) verdict = `<p class="game-verdict game-verdict--none">You didn't play this round.</p>`;
      else if ((state.winnerUids || []).includes(user.uid))
        verdict = `<p class="game-verdict game-verdict--win">🎉 You win! Your guess was ${mine.guess}.</p>`;
      else verdict = `<p class="game-verdict game-verdict--lose">Not this time — your guess was ${mine.guess}.</p>`;
      appEl.innerHTML = verdict + resultsHtml(state);
      return;
    }

    if (mine) {
      appEl.innerHTML = `
        <p class="game-submitted">✓ Submitted! <strong>${esc(mine.name)}</strong>, your guess is <strong>${mine.guess}</strong>.</p>
        <p class="game-muted">Waiting for your instructor to finalize the results… this page will update automatically.</p>`;
      return;
    }

    let savedName = "";
    try { savedName = localStorage.getItem("game-name") || ""; } catch (e) {}
    appEl.innerHTML = `
      <form id="game-form" class="game-form" novalidate>
        <label>Your name
          <input class="input" id="game-name" maxlength="60" required value="${esc(savedName)}" autocomplete="name">
        </label>
        <label>Your number (0–100)
          <input class="input" id="game-guess" type="number" min="0" max="100" step="1" inputmode="numeric" required>
        </label>
        <button class="button is-primary" type="submit">Submit</button>
        <p class="game-error" id="game-error"></p>
      </form>`;
    document.getElementById("game-form").addEventListener("submit", async e => {
      e.preventDefault();
      const errEl = document.getElementById("game-error");
      const name = document.getElementById("game-name").value.trim();
      const raw = document.getElementById("game-guess").value.trim();
      const guess = Number(raw);
      if (!name) { errEl.textContent = "Please enter your name."; return; }
      if (raw === "" || !Number.isInteger(guess) || guess < 0 || guess > 100) {
        errEl.textContent = "Please enter a whole number from 0 to 100."; return;
      }
      if (e.submitter) e.submitter.disabled = true;
      try {
        await setDoc(doc(db, "rounds", roundId, "guesses", user.uid), { name, guess, at: serverTimestamp() });
        try { localStorage.setItem("game-name", name); } catch (e2) {}
        myGuessByRound[roundId] = { name, guess };
        renderStudent();
      } catch (err) {
        errEl.textContent = state.status !== "open"
          ? "This round is already closed."
          : "Couldn't submit — you may have already played this round. Refresh the page to check.";
        if (e.submitter) e.submitter.disabled = false;
      }
    });
  }

  // ---------- Instructor view ----------
  function renderLogin() {
    if (document.getElementById("admin-login")) return;
    lastStudentKey = null;
    appEl.innerHTML = `
      <form id="admin-login" class="game-form">
        <p class="game-muted">Instructor sign-in</p>
        <label>Email <input class="input" id="admin-email" type="email" autocomplete="username" required></label>
        <label>Password <input class="input" id="admin-pass" type="password" autocomplete="current-password" required></label>
        <button class="button is-primary" type="submit">Sign in</button>
        <p class="game-error" id="admin-error"></p>
      </form>`;
    document.getElementById("admin-login").addEventListener("submit", async e => {
      e.preventDefault();
      try {
        await signInWithEmailAndPassword(auth, document.getElementById("admin-email").value, document.getElementById("admin-pass").value);
      } catch (err) {
        document.getElementById("admin-error").textContent = "Sign-in failed. Check your email and password.";
      }
    });
  }

  function renderAdmin() {
    adminEl.hidden = false;
    const open = state && state.status === "open";
    const final = state && state.status === "final";
    adminEl.innerHTML = `
      <div class="game-admin-head">
        <strong>Instructor controls</strong>
        <span class="game-badge ${open ? "is-open" : ""}">${open ? "Round open" : final ? "Finalized" : "No round"}</span>
      </div>
      <p id="admin-count" class="game-muted">${open ? "Waiting for submissions…" : ""}</p>
      <div class="game-admin-buttons">
        <button class="button is-primary" id="btn-finalize" ${open ? "" : "disabled"}>Finalize results</button>
        <button class="button" id="btn-new">${state ? "Start new round" : "Open first round"}</button>
        <button class="button is-text" id="btn-signout">Sign out</button>
      </div>
      <div id="admin-table"></div>`;

    document.getElementById("btn-signout").onclick = () => signOut(auth);
    document.getElementById("btn-new").onclick = async () => {
      if (open && !confirm("Discard the current round and start a new one?")) return;
      await setDoc(stateRef, { roundId: Date.now().toString(36), status: "open", startedAt: serverTimestamp() });
    };
    document.getElementById("btn-finalize").onclick = finalize;

    if (unsubGuesses) { unsubGuesses(); unsubGuesses = null; }
    if (state && state.roundId) {
      unsubGuesses = onSnapshot(collection(db, "rounds", state.roundId, "guesses"), snap => {
        const rows = snap.docs.map(d => ({ uid: d.id, ...d.data() }));
        const countEl = document.getElementById("admin-count");
        const tableEl = document.getElementById("admin-table");
        if (!countEl) return;
        countEl.textContent = `${rows.length} submission${rows.length === 1 ? "" : "s"} so far` + (open ? " (numbers hidden until you finalize)" : "");
        if (open) {
          tableEl.innerHTML = rows.length ? `<p class="game-names">${rows.map(r => esc(r.name)).join(" · ")}</p>` : "";
        } else if (final) {
          const winners = new Set(state.winnerUids || []);
          rows.sort((a, b) => Math.abs(a.guess - state.target) - Math.abs(b.guess - state.target));
          tableEl.innerHTML = `
            <table class="table is-fullwidth is-narrow game-table">
              <thead><tr><th>Name</th><th>Guess</th><th>Distance to ${fmt(state.target)}</th></tr></thead>
              <tbody>${rows.map(r => `<tr class="${winners.has(r.uid) ? "is-winner" : ""}">
                <td>${winners.has(r.uid) ? "🏆 " : ""}${esc(r.name)}</td><td>${r.guess}</td><td>${fmt(Math.abs(r.guess - state.target))}</td></tr>`).join("")}</tbody>
            </table>`;
        }
      });
    }
  }

  async function finalize() {
    const snap = await getDocs(collection(db, "rounds", state.roundId, "guesses"));
    const rows = snap.docs.map(d => ({ uid: d.id, ...d.data() }));
    if (!rows.length) { alert("No submissions yet."); return; }
    const average = rows.reduce((s, r) => s + r.guess, 0) / rows.length;
    const target = (2 / 3) * average;
    const best = Math.min(...rows.map(r => Math.abs(r.guess - target)));
    const winners = rows.filter(r => Math.abs(Math.abs(r.guess - target) - best) < 1e-9);
    await setDoc(stateRef, {
      ...state,
      status: "final",
      count: rows.length,
      average,
      target,
      winningGuesses: [...new Set(winners.map(w => w.guess))].sort((a, b) => a - b),
      winners: winners.map(w => ({ name: w.name, guess: w.guess })),
      winnerUids: winners.map(w => w.uid),
      finalizedAt: serverTimestamp()
    });
  }

  // ---------- Wiring ----------
  function render() {
    if (!user) return;
    if (user.uid === ADMIN_UID) {
      renderAdmin();
      appEl.innerHTML = state && state.status === "final" ? resultsHtml(state)
        : `<p class="game-muted">Students see the entry form at this page's address without <code>?instructor</code>.</p>`;
    } else {
      adminEl.hidden = true;
      renderStudent();
    }
  }

  onAuthStateChanged(auth, async u => {
    user = u;
    if (!u) {
      if (instructorMode) renderLogin();
      else signInAnonymously(auth).catch(() => {
        appEl.innerHTML = `<p class="game-error">Couldn't connect to the game server. Please refresh the page.</p>`;
      });
      adminEl.hidden = true;
      return;
    }
    if (u.isAnonymous && instructorMode) { await signOut(auth); return; }
    render();
  });

  onSnapshot(stateRef, snap => {
    state = snap.exists() ? snap.data() : null;
    render();
  }, () => {
    appEl.innerHTML = `<p class="game-error">Couldn't load the game. Please refresh the page.</p>`;
  });
</script>
