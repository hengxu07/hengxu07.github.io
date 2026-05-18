---
title: Namicast
publishDate: 2024-12-01 00:00:00
img: /assets/namicast-1.png
img_alt: Namicast surf forecast app interface
description: |
  AI-powered surf forecast app — ask any question about any spot and get a personalized recommendation based on your board and skill level.
tags:
  - AI
  - Python
  - Full Stack
url: https://namicast.vercel.app/
github: https://github.com/hengxu07/namicast
---

Namicast is an agentic surf forecast tool built around a conversational interface. Instead of staring at raw swell charts, you just ask: *"Is San Onofre worth it tomorrow morning?"* — and the agent autonomously fetches real-time data to give you a direct, personalized answer.

## How it works

The backend runs an agentic loop powered by Claude's tool-use feature. Claude decides which tools to call and in what order based on the question — no hardcoded routing. Tools include geocoding, live swell/wind data from Stormglass, and a spot knowledge base with break type, hazards, and ideal conditions.

Responses stream token-by-token via Server-Sent Events, with live status indicators so you can see what the agent is doing as it works.

## Key features

- **Agent chat** — natural language questions answered with real data
- **Surf profile** — save your board type and skill level, pre-loaded into every response
- **Multi-turn memory** — follow-up questions work in context with 24h session TTL
- **5-day forecast** — daily scoring for trip planning
- **Session breakdown** — dawn patrol, morning, afternoon, evening comparison
- **Global spot search** — any location worldwide via geocoding

## Performance

Default spots (San Onofre, Trestles, Huntington, Malibu, Doheny, Rincon) are pre-computed and cached in PostgreSQL every 12 hours. Requests for these spots hit the DB fast path instead of making live API calls, cutting response time significantly.

## Stack

Python · FastAPI · Claude API (Anthropic) · Stormglass API · PostgreSQL · React · Railway · Vercel
