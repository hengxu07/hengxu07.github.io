---
title: Powderseek
publishDate: 2026-05-17 00:00:00
img: /assets/powderseek-1.png
img_alt: Powderseek ski trip planner interface
description: |
  AI-powered ski and snowboard trip planner — tell it how many days you have and it finds the best mountain for you, from a SoCal day trip to a 10-day Japan powder pilgrimage.
tags:
  - AI
  - React
  - Python
  - PostgreSQL
url: https://powderseek.vercel.app/
github: https://github.com/hengxu07/powderseek
---

Powderseek takes one input — how many days you have — and figures out the rest. It weighs live snow forecasts, drive and flight times, your skill level, and your budget to recommend the right mountain for your window, whether that's a quick overnight to Mammoth or a full powder trip to Hokkaido.

## Motivation

Planning a ski trip is weirdly hard. Snow reports are scattered across resort sites, travel time math is manual, and budget estimates require opening six tabs. I wanted something that could take a rough idea ("I have a long weekend and $800") and turn it into an actual recommendation — not a listicle, but a specific answer.

## How it works

Resorts are scored on four weighted signals: snow quality (new snow + 7-day accumulation + base depth), travel efficiency (flight and drive time relative to trip length), terrain match, and budget alignment. A trip-tier classifier unlocks different resort pools as the trip gets longer — local SoCal spots for a day trip, Utah and Colorado for a long weekend, and Japan or Europe for a week-plus trip.

The Claude-powered agent streams its recommendation as it reasons, uses tools to fetch fresh forecast data and compare resorts side-by-side, and persists resort context across follow-up questions so you can ask "what's the food scene like?" without losing the thread.

## Key features

- **Trip-length tiers** — day / weekend / short / medium / long / expedition, each with different reachable resort pools
- **Live snow forecasts** — 37 resorts across 5 continents refreshed every 6 hours via Open-Meteo
- **Agentic reasoning** — Claude uses tool calls to fetch forecasts, compare resorts, and save preferences mid-conversation
- **Conversational continuity** — follow-up questions stay in context; the agent remembers which resorts it ranked
- **Streaming responses** — answers stream token by token over SSE so it feels fast even on long responses

## Stack

React · TypeScript · FastAPI · PostgreSQL · Claude API (Anthropic) · Open-Meteo · Railway · Vercel
