---
## Front matter (metadata)
## Only edit fields marked as Required / Optional below

layout: post
categories: research
no_network: true
author: "AllianceAI"
show_sidebar: true
datatable: true
hero_height: is-medium
remove_hero_title: true
menubar_toc: false
link-new-tab: true
mathjax: true
hide_share_buttons: true
hero_scrim: true

# Required
# Title of the research post
title: "SpiderNoid: Crawling Control for a Humanoid"

# Short description used for previews 
description: "We enable a Unitree G1 humanoid to transition into a four-limbed crawling posture, crawl, and return to standing. The policies are trained in simulation and transfer directly to the real robot."

# Publication date (YYYY-MM-DD HH:MM:SS)
date: 2026-11-06 10:00:00

# Permalink update /your-own-title/
permalink: /spidernoid/

# Hero image shown on the post and previews
# Path should point to img/posts/post-title/
hero_fallback: /img/posts/spidernoid/spidernoid_teaser.jpg

hero_video: https://haiminhu.wordpress.com/wp-content/uploads/2026/10/spidernoid.mp4
thumbnail: /img/posts/spidernoid/spidernoid_card.jpg
video: https://haiminhu.wordpress.com/wp-content/uploads/2026/10/spidernoid.mp4

# Set to true when ready to publish
published: true

# Optional
# Set to true to feature on the homepage
featured: true

link: https://github.com/JHU-AllianceLab/humanoid-crawl-with-G1-temperature-aware#real-robot-testing
---
## Overview
We enable a Unitree G1 humanoid (29-DoF) to transition from standing into a four-limbed crawling posture, crawl forward and turn, and return to standing. Two policies, one for the stand ↔ crawl transition and one for crawling (with two gait styles), are trained in [mjlab](https://github.com/mujocolab/mjlab) with PPO and switched by a state machine with safety gates at each hand-over. The forearms serve as front legs: 3D-printed wrist braces lock the wrists and extend them into rounded feet.

Code, deployable policies, and hardware files are available on [GitHub](https://github.com/JHU-AllianceLab/humanoid-crawl-with-G1-temperature-aware#real-robot-testing).

## Contributors
Geeta Chandra Raju Bethala (demo) and Krishna Murthy Jatavallabhula (video)
