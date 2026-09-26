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

## Known limitations (roadmap)
- The classifier is a **tuned heuristic**, not a model trained on real
  labelled recordings — next step is collecting a real leak/no-leak audio
  dataset and training a small classifier (e.g. logistic regression / k-NN)
  on the same features.
- Reports are stored per-browser (`localStorage`), not on a shared backend —
  a production version needs a lightweight API (e.g. Firebase) so reports
  from different phones appear on everyone's map in real time.


