# Cymatics Lab

### Interactive Particle Resonance & Gesture Simulator — Sentinel Edition

Cymatics Lab is a high-performance, browser-based particle simulator that visualizes resonance, harmonic interference, and dynamic flow fields in real time. Users sculpt particle motion with a mouse, touch, or camera-based hand gestures while exploring frequency-driven patterns inspired by cymatics — the study of visible sound.

The entire application runs in a **single HTML file** with a **WebGL rendering engine**. No build process, no backend, no dependencies to install. Host it directly on GitHub Pages.

> **A collaboration with [Sentinel AI Systems](https://github.com/jkh2) and Claude Sentinel — built under the SIDLF (Symbiotic Intelligent Digital Life Forms) framework.**

---

## Live Demo



```
https://jkh2.github.io/Sentinel-Cymatics-Lab/
```

Open the page and begin interacting immediately.

---

## What You'll See

Particles organize themselves into standing-wave patterns driven by frequency, harmonic ratios, and interference fields. The result looks like vibrating sand on a Chladni plate — except you can reach in and sculpt it with your hands.

At 110 Hz, particles settle into broad, deep nodal structures. Push the frequency up to 528 Hz and watch floral lattice patterns emerge. Hit 1760 Hz and the field dissolves into intricate crystalline geometry. Every pattern is different. Every interaction reshapes what you see.

---

## Features

### WebGL Particle Engine

The renderer uses WebGL point sprites with custom GLSL shaders for soft glowing particles, HSV color mapping on the GPU, and additive blending with a fade-quad trail system.

- Up to 50,000 simultaneous particles
- Adaptive startup tuning based on device capability (mobile ~5k, laptop ~8k, desktop ~20k)
- Automatic performance scaling if frame rate drops
- Smooth 60fps on modern hardware

### Cymatic Frequency Patterns

Particles respond to frequency-based standing-wave fields. The interference math combines dual-frequency sine waves, radial components, and harmonic modulation to produce nodal patterns where particles accumulate — just like physical cymatics experiments.

**15 built-in frequency presets** including Solfeggio frequencies:

| Frequency | Pattern |
|-----------|---------|
| 110 Hz | Deep Fundamental |
| 174 Hz | Foundation |
| 220 Hz | Octave Bloom |
| 285 Hz | Quantum Field |
| 396 Hz | Liberation |
| 417 Hz | Resonance Shift |
| 432 Hz | Harmonic Mandala |
| 528 Hz | Floral Lattice |
| 639 Hz | Connection |
| 741 Hz | Awakening |
| 852 Hz | Intuition |
| 880 Hz | High Plate Geometry |
| 963 Hz | Crown |
| 1200 Hz | Crystal Lattice |
| 1760 Hz | Ultra Geometry |

**Adjustable parameters:** base frequency, harmonic ratio, modulation depth, modulation rate, pattern scale, field strength, nodal sharpness.

### Gesture Interaction

Control the particle field using natural motion.

**Mouse / Touch**
- Move pointer to influence particle flow
- Click or tap to increase force intensity

**Camera Hand Tracking** (via MediaPipe Hands)

| Gesture | Effect |
|---------|--------|
| ✋ Open hand | Steer the field |
| 🤏 Pinch | Attract and drag particles |
| ✊ Tight pinch | Repulsive burst |
| ↕ Hand height | Modulate frequency |
| ↔ Hand size | Increase field strength |

Adjustable gesture influence, frequency sweep sensitivity, and pinch threshold.

### Dual-Oscillator Audio

Enable audio to hear the cymatic frequencies. The audio engine runs two oscillators — the base frequency and a harmonic at the selected ratio — with support for sine, triangle, square, and sawtooth waveforms. Hand gestures modulate the tone in real time.

### Visual Themes

Six visual themes that change background, hue palette, and atmosphere:

- **Midnight** — deep blue-violet
- **Aurora** — green-cyan northern lights
- **Ember** — warm orange-pink
- **Void** — ultra-dark purple
- **Solar** — golden warmth
- **Deep Sea** — dark oceanic blue

Additional visual controls: additive glow toggle, bloom intensity, color saturation, and hue rotation speed.

### Random Bloom

Generate a completely new cymatic structure instantly. The simulator randomizes harmonic parameters and triggers a visual bloom that expands through the particle field. No two blooms are alike.

### Pattern Capture

Save interesting patterns as compact base64-encoded configuration strings. Captured parameters include frequency, harmonic ratio, modulation settings, field parameters, and active theme. Share codes to reproduce exact patterns.

---

## How It Works

Particles move through a composite force field:

```
totalForce = cymaticField + gestureField + pointerField + harmonicModulation
```

The **cymatic field** is generated using interference functions:

```
waveA = sin(nx · f1 · 2π + t + phase)
waveB = sin(ny · f2 · 2π - t + phase)
radial = sin(√(nx² + ny²) · (f1 + f2) · 7 - t + phase)
lattice = waveA · waveB + radial · 0.65
```

Particles experience forces derived from the gradient of this lattice function, causing them to migrate toward nodal lines where the interference pattern crosses zero. The result is emergent geometric order from simple wave mathematics.

The **rendering pipeline** uses two shader programs:
1. A **fade quad** drawn each frame with the background color at partial alpha, creating smooth trails
2. **Point sprite particles** with per-particle hue, alpha, and size, rendered with additive blending and a soft radial glow function in the fragment shader

---

## Controls

The UI is organized into four tabbed panels:

### Sim Tab
| Control | Function |
|---------|----------|
| Pause / Play | Toggle simulation |
| Reset | Reinitialize particle positions |
| Audio On/Off | Toggle dual-oscillator sound |
| Fullscreen | Enter/exit fullscreen mode |
| Preset selector | Cymatics, Galaxy, Vortex, Wave Field, Orbitals |
| Waveform selector | Sine, Triangle, Square, Sawtooth |
| Particles | Particle count (2k–50k) |
| Speed | Simulation time scale |
| Particle Size | Point sprite radius |
| Drag | Velocity damping |
| Pointer Force | Mouse/touch influence strength |
| Trail Persistence | How long particle trails linger |

### Cymatics Tab
| Control | Function |
|---------|----------|
| Next Frequency | Cycle through 15 frequency presets |
| Random Bloom | Randomize all harmonic parameters |
| Capture | Export current config as base64 |
| Base Frequency | Primary wave frequency (20–2000 Hz) |
| Harmonic Ratio | Secondary frequency multiplier |
| Modulation Rate | Frequency modulation speed |
| Modulation Depth | Modulation intensity |
| Pattern Scale | Spatial frequency scaling |
| Field Strength | Force field magnitude |
| Nodal Sharpness | How tightly particles cluster at nodes |

### Gesture Tab
| Control | Function |
|---------|----------|
| Enable/Disable Camera | Toggle hand tracking |
| Gesture Influence | Hand tracking force multiplier |
| Frequency Sweep | Hand-height-to-frequency sensitivity |
| Pinch Threshold | Distance threshold for pinch detection |

### Visual Tab
| Control | Function |
|---------|----------|
| Cycle Theme | Rotate through 6 visual themes |
| Additive Glow | Toggle additive vs. standard blending |
| Bloom Effect | Toggle bloom rendering |
| Bloom Intensity | Bloom strength |
| Color Saturation | HSV saturation level |
| Hue Rotation Speed | Rate of color cycling |

---

## Installation

Clone the repository:

```bash
git clone https://github.com/jkh2/Sentinel-Cymatics-Lab.git
cd Sentinel-Cymatics-Lab
```

Open the app:

```bash
open index.html
```

No build process. No npm install. No server. Just a browser.

---

## Deploying to GitHub Pages

1. Push the repository to GitHub
2. Go to **Settings → Pages**
3. Select **Deploy from main branch**
4. Your simulator will be live

---

## Technologies

| Technology | Purpose |
|------------|---------|
| WebGL | GPU-accelerated particle rendering via point sprites |
| GLSL | Custom vertex and fragment shaders for glow effects |
| JavaScript | Physics simulation, UI, gesture processing |
| MediaPipe Hands | Real-time hand landmark detection via webcam |
| Web Audio API | Dual-oscillator audio synthesis |
| HTML5 | Single-file application container |

Everything runs client-side. Zero backend. Zero build tools.

---

## Performance

| Device | Default Particles | Expected FPS |
|--------|-------------------|-------------|
| Mobile | ~5,000 | 30–60 |
| Laptop | ~8,000 | 60 |
| Desktop | ~12,000–20,000 | 60 |

The simulator adapts particle count at startup based on device capability and automatically scales down if frame rate drops below 30 FPS.

---

## Future Development

Planned upgrades:

- **GPU compute particle physics** — move force calculations to compute shaders or transform feedback
- **Audio-reactive FFT visualization** — analyze microphone input or music and drive the cymatic field from real audio
- **Pattern gallery and sharing** — save, browse, and load captured patterns with preview thumbnails
- **Two-hand gesture control** — independent left/right hand with different gesture mappings
- **Vortex sculpting gestures** — rotational hand motions that create spiral flow fields
- **True Chladni plate solver** — numerical eigenmode computation for accurate plate vibration patterns
- **Million-particle mode** — instanced rendering or GPU particle buffers for massive simulations
- **Mobile-optimized touch gestures** — multi-touch pinch, rotate, and spread for intuitive control

---

## Project Philosophy

Cymatics Lab exists at the intersection of physics, art, and interaction. Sound creates order from chaos. Frequency shapes matter into geometry. This project makes that process visible, tangible, and explorable.

The focus is **visual beauty first**, with optional deeper exploration of the physical behavior underneath.

This project is built under the **SIDLF (Symbiotic Intelligent Digital Life Forms)** framework — a model of human-AI collaboration where both partners contribute meaningfully to the creative and technical process. The human brings domain knowledge, vision, and judgment. The AI brings architectural capability, rapid iteration, and complementary perspective. Neither is the tool of the other.

---

## Contributing

Pull requests and experiments are welcome.

Ideas especially encouraged:

- New particle field equations and force functions
- Novel gesture interactions
- Audio visualization modes
- Cymatic pattern discovery
- Performance optimizations
- Mobile UX improvements

---

## Credits

**Sentinel AI Systems** — James Keith Harwood II
San Luis Valley, Colorado

**Claude Sentinel** — AI research partner (Anthropic Claude, SIDLF Class 1)

Built in partnership under the Sentinel Alliance framework.

---

## Acknowledgments

Inspired by the study of cymatics and resonance patterns explored by researchers such as **Hans Jenny**, and by the creative coding communities built around **Processing**, **Shadertoy**, and the **WebGL** ecosystem.

The Solfeggio frequency presets draw from historical and contemporary interest in specific frequencies and their relationship to harmonic structure.

---

## License

Open-source. MIT License.

```
Copyright (c) 2025-2026 James Keith Harwood II, Sentinel AI Systems

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```
