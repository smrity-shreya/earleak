# EarLeak : Acoustic Leak Detection

Built for **EcoLogic 1.0** (Mercer | Mettl hackathon) — Water theme.

EarLeak turns any phone's microphone into a leak sensor. It listens to a tap,
pipe or tank for 3 seconds, classifies whether it has a leak's steady
high-frequency hiss, estimates litres/day wasted, and lets citizens report it
to a shared city leak map — giving municipal crews a priority-sorted repair
queue instead of a random complaint inbox.

No smart meter, no hardware, no app install — it runs entirely in the
browser.

## Live demo
https://smrity-shreya.github.io/earleak/

## GitHub link
https://github.com/smrity-shreya/earleak.git

## Features
- **Listen** — real-time mic recording + Web Audio analysis (signal energy,
  high-frequency hiss %, steadiness) classifies Leak (Low/Med/High) or Clear
- **Demo samples** — synthetic "leaking tap" / "healthy tap" buttons for
  demoing without a real leak nearby
- **City Map** — crowdsourced leak reports plotted as survey-style pins
- **Repair Queue** — reports sorted by estimated litres/day lost
- **Validation & Impact tab**
  - Live, re-runnable validation suite (20 synthetic labelled samples →
    accuracy / precision / recall / confusion matrix)
  - Live network simulation (streams in simulated citizen scans to preview
    what a multi-device deployment would look like)
  - Ward-level impact projection (litres/₹/CO₂e) and commercial model

## Tech stack
Single-file HTML/CSS/JavaScript. No build step, no backend, no dependencies.
Uses the native Web Audio API (`AnalyserNode`) for audio feature extraction
and `localStorage` for persisting reports in the browser.
