# Physarum Polycephalum Simulator

A real-time, interactive slime mold simulation built with WebGL and vanilla JavaScript in a single HTML file. Agents grow outward from a central point in dendritic, tree-like branching patterns — inspired by the network-forming behavior of *Physarum polycephalum*.

![Physarum](https://img.shields.io/badge/WebGL-Simulation-6b5744) ![License](https://img.shields.io/badge/license-MIT-blue)
<img width="1707" height="930" alt="Screenshot 2026-02-19 at 6 04 30 PM" src="https://github.com/user-attachments/assets/8a081562-67dc-436a-af52-d0466b6e0f1c" />

## Demo

Open `slime.html` in any modern browser. No build step, no dependencies, no server required.

## Features

- **Dendritic growth** — Agents start dormant and activate gradually, growing outward from the center in fractal branching patterns
- **Interactive mouse growth** — Move your cursor over the canvas to spawn new branch sources; tendrils grow outward from wherever you hover
- **Microscope aesthetic** — Sepia/brown color palette with animated film grain, mimicking a real microscope slide
- **Full parameter control** — 9 sliders to shape the organism in real time:

| Slider | What it does |
|---|---|
| **Growth Rate** | How many dormant agents activate per frame — controls how fast the organism expands |
| **Move Speed** | How fast active agents travel |
| **Trail Persistence** | How long trails linger before fading (higher = thicker veins) |
| **Fork Chance** | Probability of an agent branching off each frame |
| **Fork Angle** | How sharp the fork is when it happens |
| **Branch Spread** | Randomness added to fork angles (higher = more chaotic) |
| **Sensor Angle** | How wide agents scan for existing trails |
| **Sensor Distance** | How far ahead agents sense trails |
| **Turn Speed** | How sharply agents steer toward detected trails |

- **Reset** clears everything and regrows from center
- **Random** shuffles all parameters for surprising new patterns

## How It Works

1. **Agents** launch from a growth source (center or mouse) in random radial directions
2. Each agent **deposits trail** as it moves, creating visible paths
3. Agents **sense nearby trails** and steer toward them (Physarum chemotaxis), reinforcing popular paths into thick veins
4. Agents occasionally **fork** — sharply changing direction to create sub-branches
5. Trails **decay** over time, so only reinforced paths persist
6. A **WebGL blur shader** diffuses the trail map each frame for smooth, organic visuals
7. A **sepia render shader** inverts the output (dark trails on cream background) and adds film grain

The combination of trail-following, forking, and decay naturally produces fractal branching structures similar to neurons, river deltas, and real slime mold networks.

## Requirements

- Any modern browser with WebGL support (Chrome, Firefox, Safari, Edge)
- No install, no build, no server — just open the HTML file

## License

MIT
