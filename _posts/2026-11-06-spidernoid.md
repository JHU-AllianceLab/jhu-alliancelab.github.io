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
title: "SpiderNoid: Temperature-Aware Crawling Control for a Humanoid"

# Short description used for previews 
description: "We teach a Unitree G1 humanoid to walk, get down onto all fours, crawl, and stand back up. Policies are trained in simulation against a model of motor heating, so the robot can hold still and crawl for long sessions without tripping its motors' thermal cut-off, and they transfer directly to the real robot."

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
We teach a Unitree G1 humanoid (29-DoF) to walk, get down onto all fours, crawl, and stand back up. Three policies (walk, stand ↔ crawl, and crawl) are trained in [mjlab](https://github.com/mujocolab/mjlab) with PPO and switched by a state machine with safety gates at each hand-over. The forearms serve as front legs: 3D-printed wrist braces lock the wrists and extend them into rounded feet.

A key challenge is motor heating. Our first real-robot crawl tripped the motors' 85 °C thermal stop while the robot was simply holding still, because nothing in training accounted for sustained load. We therefore fine-tune the policies against a thermal model of every motor, penalizing instantaneous and sustained heat and keeping joints away from their end stops. This spreads load across motors and lowers the peak estimated motor temperature from 48 °C to 31 °C, allowing long crawling sessions on the real robot.

Code, deployable policies, and hardware files are available on [GitHub](https://github.com/JHU-AllianceLab/humanoid-crawl-with-G1-temperature-aware#real-robot-testing).

## Contributors
Geeta Chandra Raju Bethala (demo) and Krishna Murthy Jatavallabhula (video)
