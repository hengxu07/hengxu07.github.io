---
title: Powderseek iOS
publishDate: 2026-05-18 00:00:00
img: /assets/powderseek-ios-1.png
img_alt: Powderseek iOS app showing a ski resort recommendation
img_position: center top
img_fit: contain
description: |
  Native SwiftUI companion to Powderseek — real-time AI resort recommendations, SSE streaming, and a full resort detail sheet, built as a first iOS project.
tags:
  - iOS
  - Swift
  - AI
github: https://github.com/hengxu07/powderseek-ios
---

Native iOS companion to [Powderseek](https://powderseek.vercel.app/), built as my first SwiftUI project. It connects to the same FastAPI backend and delivers the same AI-powered resort recommendations in a native mobile interface.

## Motivation

After building the web app, I wanted to learn iOS development — and Powderseek felt like the right project to do it with. It has enough complexity to be interesting (streaming, async networking, multi-sheet navigation) without being so large that the learning gets lost in the codebase.

## Architecture

The app follows SwiftUI MVVM. A `@MainActor ObservableObject` view model drives all UI state, keeping every property update on the main thread without manual `DispatchQueue.main` calls. Networking is handled through a single `APIClient` backed by `URLSession`.

The most interesting part is SSE streaming: Swift's modern `URLSession.bytes(for:).lines` API gives an `AsyncBytes` sequence that can be iterated with `for try await` — a clean fit for the server-sent event format the backend emits. Each text chunk is appended directly to the last message in the `@Published` messages array, which triggers SwiftUI to re-render only the affected bubble.

## Key features

- **Streaming chat** — responses stream token-by-token; a pulsing dot indicates the assistant is still typing
- **Trip form sheet** — set dates, origin airport, skill level, and budget using native pickers
- **Resort chips** — tappable pills appear below each assistant message; matched by scanning bold text against a resort name map with fallback prefix logic
- **Resort detail sheet** — 7-day snow bar chart, stacked difficulty bar, mountain stats, terrain and vibe tags
- **Ski-only and closed-season banners** — visual warnings when a resort doesn't allow snowboarding or is outside its season
- **Session persistence** — session ID stored in `UserDefaults` so conversation context survives app restarts

## What I learned

- SwiftUI's declarative model feels similar to React but the reactivity is more explicit — you have to opt into observation with `@Published` rather than state being implicitly tracked
- `async`/`await` in Swift is syntactically close to JavaScript but the structured concurrency model (actors, task groups) is more rigorous
- `AttributedString(markdown:)` handles inline formatting well but doesn't create visual paragraph breaks — rendering paragraphs as separate `Text` views in a `VStack` was the fix
- Xcode's simulator + Instruments tooling is excellent for profiling; breakpoints in async code work reliably

## Stack

Swift · SwiftUI · URLSession (async/await) · FastAPI (shared backend) · Claude API
