---
title: Dokkai
publishDate: 2024-06-01 00:00:00
img: /assets/dokkai-1.png
img_alt: Dokkai Japanese reading assistant interface
description: |
  AI-powered Japanese reading assistant — upload any text or PDF and get vocabulary extraction, grammar analysis, JLPT level assessment, and auto-generated quizzes.
tags:
  - AI
  - Python
  - API
---

Dokkai (読解) is a reading comprehension tool for Japanese learners. Upload a PDF or paste text, and the API breaks it down: key vocabulary with furigana and English meanings, grammar patterns with explanations, JLPT difficulty assessment from N5 to N1, and multiple-choice quizzes generated on demand.

## Motivation

Japanese reading practice often requires jumping between a dictionary, a grammar reference, and a grading rubric. Dokkai collapses all of that into a single API call, making it easier to work through native material without constant context-switching.

## Key features

- **Vocabulary extraction** — key words with readings (furigana) and English definitions
- **Grammar analysis** — patterns identified with explanations and usage examples
- **JLPT assessment** — automatic difficulty grading from N5 (beginner) to N1 (advanced)
- **Quiz generation** — multiple-choice questions with smart caching so repeat requests are instant
- **Semantic search** — ChromaDB vector store for finding related content across uploaded documents

## Stack

Python · FastAPI · Claude API (Anthropic) · ChromaDB · SQLite · Railway
