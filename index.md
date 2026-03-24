---
title: "<span class='accent'>Alliance AI Lab</span>"
subtitle: "<span class='accent'>We work on the algorithmic foundations of learning and interaction for <span class='secondary-accent'>safety-assured</span> and <span class='secondary-accent'>collaborative</span> embodied AI systems.</span>"
layout: page
show_sidebar: false
hide_footer: false
hero_video: https://haiminhu.wordpress.com/wp-content/uploads/2026/03/alliance_26.mp4
hero_fallback: img/jhu-homewood.jpg
hero_link: /research/
hero_link_text: Explore Our Work
hero_scrim: false
home: true
---

# About Us
<div class="about-us-block">
  <img src="{{ site.baseurl }}/img/alliance-logo.png" alt="Alliance AI Lab logo" class="about-logo">
  <div class="about-text" markdown="1">
Welcome to the Alliance (Algorithmic Learning and Interaction for Assured & Collaborative Embodied) AI Lab at Johns Hopkins University! Our mission is to enable human-centered embodied AI systems that are verifiable, deployable, and trustworthy in real-world settings. Towards this goal, we work on new algorithms, theorems, and systems grounded in dynamic game theory, integrating insights from reinforcement learning, generative AI, control-theoretic safety, and numerical optimization. <span style="color: var(--jhu-blue-mid); font-weight: 600;">We envision a future where humans and robots learn and grow together.</span>


We are proud to be part of the [Data Science and AI Institute](https://ai.jhu.edu/), [Laboratory for Computational Sensing and Robotics](https://lcsr.jhu.edu/), and [Institute for Assured Autonomy](https://iaa.jhu.edu/) at [Johns Hopkins University](https://www.jhu.edu).
  </div>
</div>

<video controls playsinline preload="metadata" poster="{{ site.baseurl }}/img/alliance-ai-lab-teaser.png" style="width:50%; display:block; margin:0 auto 4rem; border-radius:8px;">
  <source src="https://haiminhu.wordpress.com/wp-content/uploads/2026/03/alliance_ai_lab_haimin_hu.mp4" type="video/mp4">
</video>

# Highlights
{% assign highlights = site.posts
  | where:"featured", true
  | sort: "date"
  | reverse
%}

<div class="columns is-multiline">
  {% for post in highlights %}
    <div class="column is-3-desktop is-6-tablet">
      {% include post-card.html %}
    </div>
  {% endfor %}
</div>


# News

<ul class="news-list">
  <li><span class="news-date">Mar 2026</span> The Alliance AI Lab website is launched!</li>
</ul>

<div class="linkedin-scroll">

  <div class="linkedin-item">
    <iframe 
      src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7394439563202482176?collapsed=1"
      height="400"
      width="400"
      frameborder="0"
      allowfullscreen
    ></iframe>
  </div>

  <div class="linkedin-item">
     <iframe 
      src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7366199418154323970?collapsed=1"
      height="400"
      width="400"
      frameborder="0"
      allowfullscreen
    ></iframe>
  </div>
 
  
  <div class="linkedin-item">
    <iframe 
    src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7363672942880137216?collapsed=1"
    height="400"
    width="400"
    frameborder="0"
    allowfullscreen
    ></iframe>
  </div>
 
  
  <div class="linkedin-item">
    <iframe 
    src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7329634207301828608?collapsed=1"
    height="400"
    width="400"
    frameborder="0"
    allowfullscreen
  ></iframe>
  </div>

  <div class="linkedin-item">
    <iframe 
    src="https://www.linkedin.com/embed/feed/update/urn:li:activity:7321707279186079744?collapsed=1"
    height="400"
    width="400"
    frameborder="0"
    allowfullscreen
  ></iframe>
  </div>
 
</div>
