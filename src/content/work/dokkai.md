---
title: Dokkai
publishDate: 2024-06-01 00:00:00
img: /assets/dokkai-1.png
img_alt: Dokkai Japanese reading assistant interface
images:
  - src: /assets/dokkai-2.png
    alt: Dokkai grammar analysis view
  - src: /assets/dokkai-3.png
    alt: Dokkai vocabulary list
  - src: /assets/dokkai-4.png
    alt: Dokkai quiz interface
description: |
  AI-powered Japanese reading assistant — upload any text or PDF and get vocabulary extraction, grammar analysis, JLPT level assessment, and auto-generated quizzes.
tags:
  - AI
  - Python
  - API
url: https://dokkai-lilac.vercel.app/
github: https://github.com/hengxu07/dokkai
---

Dokkai (読解) is a reading comprehension tool for Japanese learners. Upload a PDF or paste text, and the API breaks it down: key vocabulary with furigana and English meanings, grammar patterns with explanations, JLPT difficulty assessment from N5 to N1, and multiple-choice quizzes generated on demand.

## Motivation

I've been learning Japanese on and off for a few years — drawn in through anime, deepened by trips to Japan, and kept going by how genuinely interesting the language is. The problem I kept running into: reading native material meant constantly switching between a dictionary, a grammar reference, and some mental model of my current JLPT level. Dokkai collapses all of that into a single API call so I can actually focus on reading.

## Key features

- **Vocabulary extraction** — key words with readings (furigana) and English definitions
- **Grammar analysis** — patterns identified with explanations and usage examples
- **JLPT assessment** — automatic difficulty grading from N5 (beginner) to N1 (advanced)
- **Quiz generation** — multiple-choice questions with smart caching so repeat requests are instant
- **Semantic search** — ChromaDB vector store for finding related content across uploaded documents

## Stack

Python · FastAPI · Claude API (Anthropic) · ChromaDB · SQLite · Railway
