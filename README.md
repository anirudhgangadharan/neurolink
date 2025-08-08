NeuroLink
A minimal, production-ready HTML5 puzzle game
Overview
NeuroLink is a browser-based puzzle/action hybrid where you connect neural nodes to stabilize a central hub before energy or time runs out. Built as a single-file deployable (index.html), it combines clean ES6 architecture, deterministic procedural generation, performance-conscious rendering, and WebAudio SFX — all without external dependencies.
Design Philosophy

Zero build step — works on any static host (GitHub Pages, Netlify, Vercel, local file)
Readable, maintainable, extensible code structure
Responsive and accessible out of the box
Procedural levels with deterministic seeding for reproducibility
Canvas + requestAnimationFrame for smooth, device-scaled rendering

Features

Core Gameplay — Connect nodes, send pulses, manage energy/time to stabilize the hub
Procedural Level Generator — Deterministic seed-based layouts per difficulty/level
Performance-First — Device pixel-ratio scaling, minimal GC pressure, no blocking loops
WebAudio SFX — No asset downloads, pure JS-generated tones
Responsive Design — Works on desktop, tablet, mobile; keyboard + touch controls
Accessibility — ARIA labels, focus styles, keyboard navigation
Data Persistence — Saves best score & progress in localStorage

How to Play

Start Game — Click Start or press Space
Send Pulse — Click/tap on a node (or drag to another node) to charge it
Goal — Charge the hub node above threshold while keeping all nodes alive
Constraints — You have limited energy and time. Use both wisely
Advance — Complete a level to progress; difficulty scales automatically

Controls

Click / Tap — Select or pulse a node
Drag — Create a link between two nodes
Space — Pulse the hub
R — Restart level
← / → — Switch levels

Running Locally

Clone or download the repository
Open index.html in any modern browser

No build tools required


Optionally serve with a local server for mobile/touch testing:

bashpython3 -m http.server 8080
# then open http://localhost:8080
Deployment

GitHub Pages: Push index.html to main branch, enable Pages in repo settings
Netlify/Vercel: Drag & drop folder containing index.html
Self-host: Place file on any static server — Nginx, Apache, S3 static hosting, etc.

Architecture Notes

Rendering: Canvas 2D API, batched per frame, deterministic geometry for visual consistency
Logic Loop: Fixed timestep physics (dt=1/60) with accumulator, independent render rate
Level Generation: Greedy MST + random extra links, collision-spaced node placement
Data Storage: localStorage JSON blob under neurolink:v1
Audio: Minimal oscillator/gain nodes per event, no external assets
Scaling: window.devicePixelRatio aware for crispness on HiDPI displays

License
MIT License — free to use, modify, and deploy for personal or commercial projects. Attribution appreciated but not required.
