# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML slideshow for a high school Spanish class. Single-page application with no build system.

## Critical Design Requirement

**Readability for back-of-class viewing**: All text must be large enough to read from the back of a classroom. Minimum font sizes:
- Question/verb titles: 2.8rem+
- Example sentences: 3.2rem (Lesson 2 only)
- Example sentences/body text: 1.3rem minimum (Lesson 1)
- All text uses high contrast against overlaid backgrounds

## Repository & Deployment

**GitHub:** https://github.com/jeffercized/val-spanish

**Vercel:** Hosted at `spanish.jeffluence.com`

Deploy updates with:
```bash
npx vercel --prod --yes
```

## Architecture

- `index.html` - Self-contained slideshow with embedded CSS and JavaScript
- Navigation via arrow keys, click, or swipe (touch devices)
- Background images loaded from Unsplash (requires internet)
- Google Fonts: Fraunces (display) and Outfit (body)
- Multiple lessons supported via lesson containers (lesson-1, lesson-2, etc.)
- Menu system for lesson selection

## Lessons

### Lesson 1: La Vida Contemporánea
- 20 quick-response discussion questions
- Standard slide-by-slide navigation
- Focus on contemporary leisure activities

### Lesson 2: Pretérito Indefinido
- 21 irregular verbs in preterite tense
- **Line-by-line reveal feature**: Each verb slide progressively reveals example sentences
  - First arrow press: Title appears (e.g., "IR / SER – to go / to be")
  - Subsequent presses: Reveal one example sentence per click
  - After all sentences revealed: Next press advances to next verb
  - Backward navigation: Un-reveals sentences in reverse order
- Smooth fade-in/fade-out transitions (0.5s)
- Example sentences: 3.2rem font for back-of-class readability
- Teacher has full control over timing of sentence reveals
