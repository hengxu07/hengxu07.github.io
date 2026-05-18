---
title: Powderseek
publishDate: 2026-05-17 00:00:00
img: /assets/powderseek-1.png
img_alt: Powderseek ski trip planner interface
description: |
  AI-powered ski and snowboard trip planner — tell it how many days you have and it finds the best mountain for you, from a SoCal day trip to a 10-day Japan powder pilgrimage.
tags:
  - AI
  - Python
  - API
url: https://powderseek.vercel.app/
github: https://github.com/hengxu07/powderseek
---

Powderseek takes one input — how many days you have — and figures out the rest. It weighs live snow forecasts, drive and flight times, your skill level, and your budget to recommend the right mountain for your window, whether that's a quick overnight to Mammoth or a full powder trip to Hokkaido.

## Motivation

Planning a ski trip is weirdly hard. Snow reports are scattered across resort sites, travel time math is manual, and budget estimates require opening six tabs. I wanted something that could take a rough idea ("I have a long weekend and $800") and turn it into an actual recommendation — not a listicle, but a specific answer.

## Key features

- **Trip-length aware** — optimizes recommendations for everything from a day trip to a multi-week expedition
- **Live snow forecasts** — pulls current conditions and upcoming storm windows to surface the best snow, not just the most popular resort
- **Travel time modeling** — factors in drive vs. fly tradeoffs based on your location and trip length
- **Skill-level matching** — filters and ranks terrain by ability level so beginners and advanced riders get different answers
- **Budget estimation** — accounts for lift tickets, travel, and lodging to keep recommendations realistic

## Stack

Python · FastAPI · Claude API (Anthropic)
