---
layout: post
title: "EN.601.497/697 Human-Centered Robotics: Models and Algorithms"
date: 2026-03-23 11:11:11
categories: teaching
description: "In this course, we will study fundamental concepts in human-centered robotics, with an emphasis on mathematical models of human–robot interaction and decision-making algorithms for safely deploying robots in human-populated environments."
author: "AllianceAI"
published: true
show_sidebar: false
permalink: /teaching/HCR/
image: /img/teaching/HCR/hero.png
datatable: false
hero_image: /img/teaching/HCR/hero-wide.png
remove_hero_title: true
menubar_toc: true
link-new-tab: true
mathjax: true
hide_share_buttons: true
hero_height: is-small-tall
no_network: true
hero_scrim: true
---

**Fall 2026 · 3 credits**

**Instructor:** [Prof. Haimin Hu](https://www.cs.jhu.edu/faculty/haimin-hu/)

**Level:** Graduate & Undergraduate

**Prerequisites:** EN.601.220, 601.226, linear algebra, calculus, probability.



## Course Description

In this course, we will study fundamental concepts in human-centered robotics, with an emphasis on mathematical models of human–robot interaction and decision-making algorithms for safely deploying robots in human-populated environments. We will ground these ideas in applications such as autonomous vehicles, aerial robots, and home robots.

We will start by introducing the main technical tools for robot planning and control in interactive, safety-critical settings through a game-theoretic lens. After that, we will turn our attention to two tightly coupled challenges: enabling robots to safely learn from humans and help humans learn. The course will combine seminar-style discussions of research papers and whiteboard-style lecture to introduce the key theoretical concepts, and the class project will give you an opportunity to explore the approaches covered in class and possibly combine them with your own research.

After this class, you will be familiar with the state of the art and open challenges in safe and performant human–robot interaction, and you will understand the guarantees and tradeoffs offered by different algorithmic frameworks for human-centered robotics.



## Grading

| Component | Percentage |
|:---|:---:|
| Homework assignments (3 × 10%, mix of theoretical and programming tasks) | 30% |
| Paper discussion | 5% |
| In-class debate | 5% |
| Lightning talk | 5% |
| Midterm project report | 5% |
| Final project presentation | 20% |
| Final project report | 30% |


## Reference Textbooks

*(There is no required textbook)*

- Dimitri Bertsekas, *Reinforcement Learning and Optimal Control*.
- Tamer Basar, Geert Jan Olsder, *Dynamic Noncooperative Game Theory*, 2nd Edition.



## Learning Objectives

- You will learn to **formulate human–robot interaction problems** using tools from game theory, machine learning, dynamical systems, and cognitive science.

- You will explore how different mathematical models can help **inform robot decision-making** in safety-critical, human-interactive settings.

- You will learn **principles and algorithms for ensuring safety** when deploying robots in human-populated environments, including safety filters, dynamic games, planning under uncertainty, and learning-based approaches, and understand different guarantees and tradeoffs associated with various decision-making frameworks.

- You will study **how robots can support and accelerate human learning** through strategic interactions, as well as the algorithmic principles behind it, including shared autonomy, assistance games, and active teaching methods that go beyond reactive assistance.

- Through **debate sessions**, inspired by the [ICRA Robotics Debates](https://www.roboticsdebates.org/), you will develop critical thinking about emerging challenges in modern robotics, and learn to articulate, defend, and critique competing perspectives.

- Through a **5-minute lightning talk**, modeled after common practices at major robotics conferences, you will learn to communicate technical insights concisely and prepare for future conference engagement.

- Through a semester-long project, you will learn the **full pipeline of conducting research** in human-centered robotics, including dissecting research papers, identifying limitations in existing approaches, formulating problems with suitable models, developing algorithmic solutions, and deploying and verifying them on hardware platforms. The [Alliance AI Lab](https://alliance-ai.cs.jhu.edu/) is committed to providing ongoing mentorship and equipment support for students wishing to advance their projects toward publication.



## Tentative Syllabus

<div class="table-container">
<table class="table is-fullwidth is-striped is-hoverable" style="font-size:0.85rem;">
<thead>
<tr>
  <th style="min-width:3rem">Week</th>
  <th style="min-width:5.5rem">Date</th>
  <th style="min-width:2rem">Lecture</th>
  <th style="min-width:13rem">Topic</th>
  <th style="min-width:9rem">Type</th>
  <th>Notes</th>
</tr>
</thead>
<tbody>

<!-- ── Module I ── -->
<tr class="has-background-info-light">
  <td colspan="6"><strong>Module I: Foundations of Interactive Robotics</strong></td>
</tr>

<tr>
  <td>1</td>
  <td>Aug 31</td>
  <td>1</td>
  <td>Human-centered robotics 101</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td><strong>Recommended Movie:</strong> <a href="https://www.nytimes.com/video/NYT-Presents/100000008464087/the-new-york-times-presents-elon-musks-crash-course.html" target="_blank">Elon Musk's Crash Course</a></td>
</tr>

<tr>
  <td>1</td>
  <td>Sep 2</td>
  <td>2</td>
  <td>Foundations: Dynamical systems, probability, Bayesian inference, optimal control</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td><strong>Required Reading:</strong> <a href="http://www-sop.inria.fr/members/Ian.Jermyn/philosophy/writings/Boxonmaths.pdf" target="_blank">All models are wrong. George Box (1976)</a></td>
</tr>

<tr>
  <td>2</td>
  <td>Sep 7</td>
  <td></td>
  <td><em>Labor Day 🏖️</em></td>
  <td></td>
  <td></td>
</tr>

<tr>
  <td>2</td>
  <td>Sep 9</td>
  <td>3</td>
  <td>Robotic motion planning (search, optimization, MDP/RL)</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td>
    <strong>Optional Reading 1:</strong> <a href="https://lavalle.pl/planning/" target="_blank">Planning Algorithms. LaValle (2006)</a><br>
    <strong>Optional Reading 2:</strong> <a href="https://www.annualreviews.org/content/journals/10.1146/annurev-control-053018-023825" target="_blank">A Tour of Reinforcement Learning: The View from Continuous Control. Recht (2019)</a>
  </td>
</tr>

<tr>
  <td>3</td>
  <td>Sep 14</td>
  <td>4</td>
  <td>Robot safety (Operational design domain, Safety Filters, Hamilton-Jacobi reachability, control barrier functions, model predictive control and shielding)</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td>
    <strong>Required Reading 1:</strong> <a href="https://www.researchgate.net/profile/Krzysztof-Czarnecki-2/publication/326543176_Operational_Design_Domain_for_Automated_Driving_Systems_-_Taxonomy_of_Basic_Terms/links/5b5404d345851507a7bbe6f1/Operational-Design-Domain-for-Automated-Driving-Systems-Taxonomy-of-Basic-Terms.pdf" target="_blank">Operational Design Domain for Automated Driving Systems. Czarnecki (2018)</a><br>
    <strong>Required Reading 2:</strong> <a href="https://www.annualreviews.org/content/journals/10.1146/annurev-control-071723-102940" target="_blank">The Safety Filter: A Unified View of Safety-Critical Control in Autonomous Systems. Hsu et al. (2024)</a>
  </td>
</tr>

<tr>
  <td>3</td>
  <td>Sep 16</td>
  <td>5</td>
  <td>Computing safe robot control policies (analytical, dynamic programming, learning-based)</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span><br>
    <span class="tag is-info is-light">HW release</span><br>
    <span class="tag is-primary is-light">Code demo</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> Pre-specifying an ODD for robots is a suitable way to characterize and enforce its safe operation around people.<br>
    <strong>Code Demo:</strong> Safety Filters<br>
    <strong>Optional Reading 1:</strong> <a href="https://arxiv.org/abs/2011.02082" target="_blank">DeepReach: A Deep Learning Approach to High-Dimensional Reachability. Bansal and Tomlin (2020)</a><br>
    <strong>Optional Reading 2:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/9303785" target="_blank">Learning Control Barrier Functions from Expert Demonstrations. Robey et al. (2020)</a><br>
    <strong>Homework 1:</strong> Trajectory optimization, MDP/RL, robot safety
  </td>
</tr>

<tr>
  <td>4</td>
  <td>Sep 21</td>
  <td>6</td>
  <td>Emerging robot safety methods</td>
  <td><span class="tag is-light">Paper discussion</span></td>
  <td>
    <strong>Paper 1:</strong> <a href="https://arxiv.org/abs/2502.00935" target="_blank">Generalizing Safety Beyond Collision-Avoidance via Latent-Space Reachability Analysis. Nakamura et al. (2025)</a><br>
    <strong>Paper 2:</strong> <a href="http://proceedings.mlr.press/v37/sui15.pdf" target="_blank">Safe Exploration for Optimization with Gaussian Processes. Sui et al. (2015)</a><br>
    <strong>Paper 3:</strong> <a href="https://arxiv.org/abs/2407.08735" target="_blank">Real-Time Anomaly Detection and Reactive Planning with Large Language Models. Sinha et al. (2024)</a>
  </td>
</tr>

<!-- ── Module II ── -->
<tr class="has-background-warning-light">
  <td colspan="6"><strong>Module II: The Game Theory of Human–Robot Interaction</strong></td>
</tr>

<tr>
  <td>4</td>
  <td>Sep 23</td>
  <td>7</td>
  <td>Introduction to dynamic game theory</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-primary is-light">Code demo</span>
  </td>
  <td>
    <strong>Code Demo:</strong> ILQGames, KLGames<br>
    <strong>Required Reading:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/9197129" target="_blank">Efficient Iterative Linear-Quadratic Approximations for Nonlinear Multi-Player General-Sum Differential Games. Fridovich-Keil et al. (2020)</a><br>
    <strong>Optional Reading 1:</strong> <a href="https://epubs.siam.org/doi/book/10.1137/1.9781611971132" target="_blank">Dynamic Noncooperative Game Theory. Başar and Olsder (1998)</a><br>
    <strong>Optional Reading 2:</strong> <a href="https://clearoboticslab.github.io/books/" target="_blank">Smooth Game Theory. Fridovich-Keil et al. (2024)</a><br>
    <strong>Optional Reading 3:</strong> <a href="https://arxiv.org/abs/2402.14174" target="_blank">Blending Data-Driven Priors in Dynamic Games. Lidard et al. (2024)</a>
  </td>
</tr>

<tr>
  <td>5</td>
  <td>Sep 28</td>
  <td>8</td>
  <td>Modeling HRI as a stochastic game</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td>
    <strong>Required Reading:</strong> <a href="https://web.archive.org/web/20220218155452id_/http://www.roboticsproceedings.org/rss12/p29.pdf" target="_blank">Planning for Autonomous Cars that Leverage Effects on Human Actions. Sadigh et al. (2018)</a><br>
    <strong>Optional Reading 1:</strong> <a href="https://psycnet.apa.org/record/1960-03588-000" target="_blank">Individual Choice Behavior. Luce (1959)</a><br>
    <strong>Optional Reading 2:</strong> <a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC4137788/" target="_blank">Understanding the Intentions of Others: Re-Enactment of Intended Acts by 18-Month-Old Children. Meltzoff (1995)</a>
  </td>
</tr>

<tr>
  <td>5</td>
  <td>Sep 30</td>
  <td>9</td>
  <td>Predicting human intent and motion</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-info">HW due</span>
  </td>
  <td>
    <strong>Required Reading 1:</strong> <a href="https://arxiv.org/abs/1806.00109" target="_blank">Probabilistically Safe Robot Planning with Confidence-Based Human Predictions. Fisac et al. (2018)</a><br>
    <strong>Required Reading 2:</strong> <a href="https://arxiv.org/pdf/2001.04465" target="_blank">LESS is More: Rethinking Probabilistic Models of Human Behavior. Bobu et al. (2020)</a><br>
    <strong>Optional Reading:</strong> <a href="https://proceedings.neurips.cc/paper_files/paper/2022/hash/2ab47c960bfee4f86dfc362f26ad066a-Abstract-Conference.html" target="_blank">Motion Transformer with Global Intention Localization and Local Movement Refinement. Shi et al. (2022)</a>
  </td>
</tr>

<tr>
  <td>6</td>
  <td>Oct 5</td>
  <td>10</td>
  <td>Language-enabled HRI</td>
  <td>
    <span class="tag is-light">Paper discussion</span><br>
    <span class="tag is-warning">Project proposal due</span>
  </td>
  <td>
    <strong>Paper 1:</strong> <a href="https://arxiv.org/abs/2111.03205" target="_blank">LILA: Language-Informed Latent Actions. Karamcheti et al. (2021)</a><br>
    <strong>Paper 2:</strong> <a href="https://arxiv.org/abs/2307.01928" target="_blank">Robots That Ask For Help: Uncertainty Alignment for Large Language Model Planners. Ren et al. (2023)</a><br>
    <strong>Paper 3:</strong> <a href="https://arxiv.org/abs/2403.15959" target="_blank">Risk-Calibrated Human-Robot Interaction via Set-Valued Intent Prediction. Lidard et al. (2024)</a>
  </td>
</tr>

<tr>
  <td>6</td>
  <td>Oct 7</td>
  <td>11</td>
  <td>Safety filtering around humans</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span><br>
    <span class="tag is-info is-light">HW release</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> A robot that fails less often than humans performing the same type of task should be considered safe enough for deployment.<br>
    <strong>Optional Reading 1:</strong> <a href="https://arxiv.org/pdf/2012.03390.pdf" target="_blank">On Infusing Reachability-Based Safety Assurance within Planning Frameworks for Human-Robot Vehicle Interactions. Leung et al. (2020)</a><br>
    <strong>Optional Reading 2:</strong> <a href="https://arxiv.org/pdf/2302.00171" target="_blank">Active Uncertainty Reduction for Safe and Efficient Interaction Planning: A Shielding-Aware Dual Control Approach. Hu et al. (2023)</a><br>
    <strong>Homework 2:</strong> Dynamic games, human intent modeling, POMDP
  </td>
</tr>

<tr>
  <td>7</td>
  <td>Oct 12</td>
  <td>12</td>
  <td>Cooperative games and value alignment in HRI</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td>
    <strong>Required Reading 1:</strong> <a href="https://proceedings.neurips.cc/paper_files/paper/2016/hash/c3395dd46c34fa7fd8d729d8cf88b7a8-Abstract.html" target="_blank">Cooperative Inverse Reinforcement Learning. Hadfield-Menell et al. (2016)</a><br>
    <strong>Required Reading 2:</strong> <a href="https://arxiv.org/abs/1707.06354" target="_blank">Pragmatic-Pedagogic Value Alignment. Fisac et al. (2017)</a>
  </td>
</tr>

<tr>
  <td>7</td>
  <td>Oct 14</td>
  <td>13</td>
  <td>Planning with human internal states</td>
  <td><span class="tag is-light">Paper discussion</span></td>
  <td>
    <strong>Paper 1:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/10400882" target="_blank">Contingency Games for Multi-Agent Interaction. Peters et al. (2024)</a><br>
    <strong>Paper 2:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/9801560/" target="_blank">Improving Automated Driving through POMDP Planning with Human Internal States. Sunberg and Kochenderfer (2022)</a><br>
    <strong>Paper 3:</strong> <a href="https://proceedings.mlr.press/v229/hu23b.html" target="_blank">Deception Game: Closing the Safety-Learning Loop in Interactive Robot Autonomy. Hu et al. (2023)</a>
  </td>
</tr>

<!-- ── Module III ── -->
<tr class="has-background-success-light">
  <td colspan="6"><strong>Module III: Robots that Learn from Humans</strong></td>
</tr>

<tr>
  <td>8</td>
  <td>Oct 19</td>
  <td>14</td>
  <td>Robot learning basics: model-free/model-based RL, imitation learning, diffusion policy</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-info">HW due</span>
  </td>
  <td>
    <strong>Required Reading 1:</strong> <a href="https://arxiv.org/pdf/1801.01290.pdf" target="_blank">Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor. Haarnoja et al. (2018)</a><br>
    <strong>Required Reading 2:</strong> <a href="https://arxiv.org/pdf/2301.04104" target="_blank">Mastering Diverse Domains through World Models. Hafner et al. (2023)</a><br>
    <strong>Required Reading 3:</strong> <a href="https://journals.sagepub.com/doi/full/10.1177/02783649241273668" target="_blank">Diffusion Policy: Visuomotor Policy Learning via Action Diffusion. Chi et al. (2024)</a>
  </td>
</tr>

<tr>
  <td>8</td>
  <td>Oct 21</td>
  <td>15</td>
  <td>Midterm "mini-conference": 5-min lightning talks + 2-min Q&amp;A</td>
  <td><span class="tag is-danger is-light">Lightning talks</span></td>
  <td></td>
</tr>

<tr>
  <td>9</td>
  <td>Oct 26</td>
  <td>16</td>
  <td>Safe robot learning: multi-agent RL, safety RL, RL under safety filtering, verification of neural controllers</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td>
    <strong>Required Reading 1:</strong> <a href="https://arxiv.org/abs/1703.02702" target="_blank">Robust Adversarial Reinforcement Learning. Pinto et al. (2017)</a><br>
    <strong>Required Reading 2:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/8794107" target="_blank">Bridging Hamilton-Jacobi Safety Analysis and Reinforcement Learning. Fisac et al. (2019)</a><br>
    <strong>Required Reading 3:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/9301422" target="_blank">Safety Verification and Robustness Analysis of Neural Networks via Quadratic Constraints and Semidefinite Programming. Fazlyab et al. (2020)</a><br>
    <strong>Optional Reading:</strong> <a href="https://arxiv.org/abs/2409.13867" target="_blank">MAGICS: Adversarial RL with Minimax Actors Guided by Implicit Critic Stackelberg. Wang et al. (2024)</a><br>
    <strong>Optional Reading:</strong> <a href="https://arxiv.org/abs/2510.18082" target="_blank">Provably Optimal Reinforcement Learning under Safety Filtering. Oh et al. (2025)</a><br>
    <strong>Optional Reading:</strong> <a href="https://sia-lab-git.github.io/Verification_of_Neural_Reachable_Tubes.pdf" target="_blank">Verification of Neural Reachable Tubes via Scenario Optimization and Conformal Prediction. Lin and Bansal (2024)</a>
  </td>
</tr>

<tr>
  <td>9</td>
  <td>Oct 28</td>
  <td>17</td>
  <td>Inverse RL and games</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span><br>
    <span class="tag is-info is-light">HW release</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> RL/IL is more useful than optimal control for human-centered robotics.<br>
    <strong>Required Reading:</strong> <a href="https://ai.stanford.edu/~amaas/papers/amaas_aaai.pdf" target="_blank">Maximum Entropy Inverse Reinforcement Learning. Ziebart et al. (2008)</a><br>
    <strong>Homework 3:</strong> Safe RL, inverse games
  </td>
</tr>

<tr>
  <td>10</td>
  <td>Nov 2</td>
  <td>18</td>
  <td>Learning rewards</td>
  <td><span class="tag is-light">Paper discussion</span></td>
  <td>
    <strong>Paper 1:</strong> <a href="https://arxiv.org/abs/1910.04365" target="_blank">Asking Easy Questions: A User-Friendly Approach to Active Reward Learning. Biyik et al. (2019)</a><br>
    <strong>Paper 2:</strong> <a href="https://arxiv.org/abs/2002.04833" target="_blank">Reward-Rational (Implicit) Choice: A Unifying Formalism for Reward Learning. Jeon et al. (2020)</a><br>
    <strong>Paper 3:</strong> <a href="https://arxiv.org/abs/2106.03611" target="_blank">Inferring Objectives in Continuous Dynamic Games from Noise-Corrupted Partial State Observations. Peters et al. (2021)</a>
  </td>
</tr>

<tr>
  <td>10</td>
  <td>Nov 4</td>
  <td>19</td>
  <td>RLHF, Human–AI safety<br><em>(Guest lecture: Kaiqu Liang)</em></td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> More data can enhance alignment and safety in human-centered robotics.<br>
    <strong>Required Reading:</strong> <a href="https://arxiv.org/abs/1706.03741" target="_blank">Deep Reinforcement Learning from Human Preferences. Christiano et al. (2017)</a><br>
    <strong>Required Reading:</strong> <a href="https://arxiv.org/abs/2405.09794" target="_blank">Human-AI Safety: A Descendant of Generative AI and Control Systems Safety. Bajcsy and Fisac (2024)</a><br>
    <strong>Optional Reading:</strong> <a href="https://arxiv.org/abs/2510.13727" target="_blank">From Refusal to Recovery: A Control-Theoretic Approach to Generative AI Guardrails. Pandya et al. (2025)</a><br>
    <strong>Optional Reading:</strong> <a href="https://arxiv.org/abs/2307.15217" target="_blank">Open Problems and Fundamental Limitations of Reinforcement Learning from Human Feedback. Casper et al. (2023)</a>
  </td>
</tr>

<tr>
  <td>11</td>
  <td>Nov 9</td>
  <td>20</td>
  <td>Embodied AI safety</td>
  <td><span class="tag is-light">Paper discussion</span></td>
  <td>
    <strong>Paper 1:</strong> <a href="https://arxiv.org/abs/2503.07885" target="_blank">Safety Guardrails for LLM-Enabled Robots. Ravichandran et al. (2025)</a><br>
    <strong>Paper 2:</strong> <a href="https://arxiv.org/abs/2402.17747" target="_blank">When Your AIs Deceive You: Challenges of Partial Observability in Reinforcement Learning from Human Feedback. Lang et al. (2024)</a><br>
    <strong>Paper 3:</strong> <a href="https://arxiv.org/abs/2501.08617" target="_blank">RLHS: Mitigating Misalignment in RLHF with Hindsight Simulation. Liang et al. (2025)</a>
  </td>
</tr>

<!-- ── Module IV ── -->
<tr class="has-background-danger-light">
  <td colspan="6"><strong>Module IV: Robots that Help Humans Learn</strong></td>
</tr>

<tr>
  <td>11</td>
  <td>Nov 11</td>
  <td>21</td>
  <td>Legibility and predictability</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-info">HW due</span>
  </td>
  <td>
    <strong>Required Reading:</strong> <a href="https://ieeexplore.ieee.org/abstract/document/6483603" target="_blank">Legibility and Predictability of Robot Motion. Dragan et al. (2013)</a>
  </td>
</tr>

<tr>
  <td>12</td>
  <td>Nov 16</td>
  <td>22</td>
  <td>AI coaching</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> Explicit representations of human skill level are essential for a robot to effectively teach humans.
  </td>
</tr>

<tr>
  <td>12</td>
  <td>Nov 18</td>
  <td>23</td>
  <td>Robots that assist and teach</td>
  <td><span class="tag is-light">Paper discussion</span></td>
  <td>
    <strong>Paper 1:</strong> <a href="https://openreview.net/pdf?id=adf3pO9baG" target="_blank">Dreaming to Assist: Learning to Align with Human Objectives for Shared Control in High-Speed Racing. DeCastro et al. (2024)</a><br>
    <strong>Paper 2:</strong> <a href="https://arxiv.org/pdf/2410.01608" target="_blank">Computational Teaching for Driving via Multi-Task Imitation Learning. Gopinath et al. (2024)</a><br>
    <strong>Paper 3:</strong> <a href="https://www.roboticsproceedings.org/rss21/p093.pdf" target="_blank">Safety with Agency: Human-Centered Safety Filter with Application to AI-Assisted Motorsports. Oh et al. (2025)</a>
  </td>
</tr>

<tr>
  <td>13</td>
  <td>Nov 23</td>
  <td></td>
  <td><em>Fall Recess 🏖️</em></td>
  <td></td>
  <td></td>
</tr>

<tr>
  <td>13</td>
  <td>Nov 25</td>
  <td></td>
  <td><em>Fall Recess 🏖️</em></td>
  <td></td>
  <td></td>
</tr>

<tr>
  <td>14</td>
  <td>Nov 30</td>
  <td>24</td>
  <td>Guest lecture on AI coaching / Human–AI co-evolution</td>
  <td><span class="tag is-success is-light">Lecture</span></td>
  <td></td>
</tr>

<tr>
  <td>14</td>
  <td>Dec 2</td>
  <td>25</td>
  <td>Course wrap-up</td>
  <td>
    <span class="tag is-success is-light">Lecture</span><br>
    <span class="tag is-warning is-light">Debate</span>
  </td>
  <td>
    <strong>Debate Proposition:</strong> AI systems should intentionally allow users to fail in order to promote long-term learning and independence when coaching humans.<br>
    <strong>Required Reading:</strong> <a href="https://www.annualreviews.org/content/journals/10.1146/annurev-psych-010416-044022" target="_blank">Learning from Errors. Metcalfe (2017)</a><br>
    <strong>Required Reading:</strong> <a href="https://academics.hamilton.edu/documents/themundanityofexcellence.pdf" target="_blank">The Mundanity of Excellence. Chambliss (1989)</a>
  </td>
</tr>

<tr>
  <td>15</td>
  <td>Dec 7</td>
  <td>26</td>
  <td>Project Final Presentations 1</td>
  <td><span class="tag is-danger is-light">Project presentation</span></td>
  <td></td>
</tr>

<tr>
  <td>15</td>
  <td>Dec 9</td>
  <td>27</td>
  <td>Project Final Presentations 2</td>
  <td><span class="tag is-danger is-light">Project presentation</span></td>
  <td></td>
</tr>

</tbody>
</table>
</div>
