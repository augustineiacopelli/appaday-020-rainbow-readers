# 018 · Rainbow Readers

**AppADay** · Day 18 · Category: G (Games and Interactive)

## What It Does

Rainbow Readers is a four-level phonics game for early readers ages 4–7. Level 1 asks players to tap the correct starting letter for a pictured word. Level 2 asks them to identify the full matching word. Level 3 introduces finger tracing — a thick dotted guide letter appears on a canvas and the player traces over it in rainbow ink. Level 4 extends tracing to whole words, one letter at a time, with a progress pip row showing which letters are done.

## How to Use

Tap answer buttons in Levels 1 and 2. In Levels 3 and 4, draw over the dotted guide letter with your finger, then tap Check. The app measures both how much of the letter you covered and how precisely your strokes stayed on it. Tap Clear to try again, or Next to move on after a result. A star is earned for each correct answer. Finishing all four levels triggers a confetti celebration.

## Technical Notes

- Vanilla HTML/CSS/JS, no frameworks, no external dependencies beyond Google Fonts (Nunito)
- Web Speech API selects a female voice by name (Samantha, Karen, Google UK English Female, etc.) with fallback chain across iOS, Android, and desktop
- Tracing uses two canvas layers: a visible guide canvas and a hidden hit-mask canvas built by copying guide pixels directly — no font re-rendering, no timing dependency
- Coverage check: 55% of guide pixels must be painted over; precision check: 72% of drawn strokes must land within 8px of the guide letter; stroke length capped at 3× canvas width to catch scribbling
- Guide letter rendered with a thick 26px stroke so crossbars and thin letter strokes have sufficient pixel area for reliable coverage math
- 19-word pool, all unambiguous emoji-to-word mappings verified against what a 6-year-old would name each emoji
- Dyslexia-informed design: Nunito typeface, large tap targets, no time pressure, correct answer always shown in green on wrong tap

## Definition of Complete

- [x] Four levels render and progress correctly
- [x] Tracing check rejects scribbles and off-letter strokes
- [x] Tracing check passes genuine letter traces
- [x] Star reward system activates per correct answer
- [x] Confetti and voice celebrate completion
- [x] Female voice selected across iOS, Android, and desktop
- [x] Mobile-friendly at 375px viewport
- [x] Deployed to GitHub Pages
