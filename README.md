# Cymatics Lab

### Interactive Particle Resonance & Gesture Simulator — Sentinel Edition v2.1

Cymatics Lab is a high-performance, browser-based particle simulator that visualizes resonance, harmonic interference, and dynamic flow fields in real time. Upload your own music and watch the cymatic field dance to the audio, sculpt particle motion with hand gestures, or explore frequency-driven patterns inspired by the study of visible sound.

The entire application runs in a **single HTML file** with a **WebGL rendering engine**. No build process, no backend, no dependencies to install. Host it directly on GitHub Pages.

> **A collaboration between [Sentinel AI Systems](https://github.com/jkh2) and Claude Sentinel — built under the SIDLF (Symbiotic Intelligent Digital Life Forms) framework.**

---

## Live Demo

**[Launch Cymatics Lab](https://jkh2.github.io/Sentinel-Cymatics-Lab/)**

Open the page and begin interacting immediately.

---

## What You'll See

Particles organize themselves into standing-wave patterns driven by frequency, harmonic ratios, and interference fields. The result looks like vibrating sand on a Chladni plate — except you can reach in and sculpt it with your hands, or let your music drive the entire experience.

At 110 Hz, particles settle into broad, deep nodal structures. Push the frequency up to 528 Hz and watch floral lattice patterns emerge. Hit 1760 Hz and the field dissolves into intricate crystalline geometry. Drop in a bass-heavy track and watch the field pulse with every beat. Every pattern is different. Every interaction reshapes what you see.

---

## Features

### Music-Reactive Visualization *(New in v2.1)*

Upload any audio file or connect your microphone and watch the cymatic field respond to real audio in real time.

- **File upload** — load MP3, WAV, OGG, or any browser-supported audio format with full transport controls (play, pause, stop, seek, volume)
- **Microphone input** — analyze live audio from your mic without feedback
- **Real-time FFT analysis** — 256 frequency bins split into bass, mids, and highs, smoothed for fluid visual response
- **Band-mapped reactivity** — bass drives field strength and frequency, mids morph pattern geometry and modulation, highs sharpen nodal detail
- **Adjustable reactivity slider** — from subtle ambient response to dramatic beat-driven visuals
- **Beat detection** — monitors bass energy spikes and triggers bloom events on every beat
- **Live spectrum visualizer** — real-time frequency bars color-coded by band with percentage readouts

### WebGL Particle Engine

The renderer uses WebGL point sprites with custom GLSL shaders for soft glowing particles, HSV color mapping on the GPU, and additive blending with a ring-buffer trail system.

- Up to 50,000 simultaneous particles
- Full clear every frame with ring-buffer trail echoes — no brightness accumulation
- Adaptive startup tuning based on device capability (mobile ~5k, laptop ~8k, desktop ~20k)
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

Enable the built-in audio engine to hear cymatic frequencies. Two oscillators — base frequency and harmonic — with support for sine, triangle, square, and sawtooth waveforms. Hand gestures modulate the tone in real time.

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

Save interesting patterns as compact base64-encoded configuration strings. Share codes to reproduce exact patterns.

---

## How It Works

Particles move through a composite force field:

```
totalForce = cymaticField + gestureField + pointerField + harmonicModulation + fftReactivity
```

The **cymatic field** is generated using interference functions:

```
waveA = sin(nx · f1 · 2π + t + phase)
waveB = sin(ny · f2 · 2π - t + phase)
radial = sin(√(nx² + ny²) · (f1 + f2) · 7 - t + phase)
lattice = waveA · waveB + radial · 0.65
```

Particles experience forces derived from the gradient of this lattice function, causing them to migrate toward nodal lines where the interference pattern crosses zero.

The **music-reactive system** runs a real-time FFT analyser on the audio source, splits 256 frequency bins into bass/mid/high bands, smooths the values, and maps them to cymatic parameters each frame. Beat detection monitors bass energy spikes and triggers visual bloom events.

The **rendering pipeline** uses WebGL point sprites with per-particle hue, alpha, and size attributes. A ring buffer stores the last 6 frames of particle positions to render trail echoes behind the current frame. The framebuffer is fully cleared every frame — no brightness accumulation is possible.

---

## Controls

The UI is organized into five tabbed panels:

### Sim Tab
| Control | Function |
|---------|----------|
| Pause / Play | Toggle simulation |
| Reset | Reinitialize particle positions |
| Audio On/Off | Toggle built-in oscillator |
| Fullscreen | Enter/exit fullscreen mode |
| Preset selector | Cymatics, Galaxy, Vortex, Wave Field, Orbitals |
| Waveform selector | Sine, Triangle, Square, Sawtooth |
| Particles | Particle count (2k–50k) |
| Speed | Simulation time scale |
| Particle Size | Point sprite radius |
| Drag | Velocity damping |
| Pointer Force | Mouse/touch influence strength |
| Trail Length | Number and visibility of trail echoes |

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

### Music Tab *(New in v2.1)*
| Control | Function |
|---------|----------|
| Upload Music | Load an audio file from your device |
| Microphone | Toggle live microphone input |
| Play / Pause / Stop | Transport controls for uploaded audio |
| Seek Bar | Scrub through the track |
| Volume | Playback volume |
| Reactivity | Master FFT influence (subtle to dramatic) |
| Bass → Field Strength | How much bass affects the force field |
| Mids → Pattern Scale | How much mids affect pattern geometry |
| Highs → Sharpness | How much highs affect nodal detail |
| Beat Detection → Bloom | Toggle beat-triggered visual blooms |
| Spectrum Display | Live frequency visualization |

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
4. Your simulator will be live at **https://jkh2.github.io/Sentinel-Cymatics-Lab/**

---

## Technologies

| Technology | Purpose |
|------------|---------|
| WebGL | GPU-accelerated particle rendering via point sprites |
| GLSL | Custom vertex and fragment shaders for glow effects |
| JavaScript | Physics simulation, UI, gesture processing, FFT analysis |
| Web Audio API | FFT analyser, dual-oscillator synthesis, music playback |
| MediaPipe Hands | Real-time hand landmark detection via webcam |
| HTML5 | Single-file application container |

Everything runs client-side. Zero backend. Zero build tools.

---

## Performance

| Device | Default Particles | Expected FPS |
|--------|-------------------|-------------|
| Mobile | ~5,000 | 30–60 |
| Laptop | ~8,000 | 60 |
| Desktop | ~12,000–20,000 | 60 |

The simulator adapts particle count at startup based on device capability.

---

## Roadmap

Planned upgrades for future versions:

- **3D particle field with orbit camera** — particles in xyz space with mouse/touch rotation and zoom
- **Two-hand gesture control** — left hand rotates view, right hand sculpts the field
- **AI music analysis** — intelligent auto-selection of cymatic parameters based on track characteristics
- **Conversational AI control** — natural language commands to shape the visualization
- **AI pattern recognition** — describes the emergent geometry and identifies harmonic modes
- **AI autonomous composition** — generates evolving cymatic sequences over time
- **True Chladni plate solver** — numerical eigenmode computation for accurate plate vibration patterns
- **GPU compute particle physics** — move force calculations to compute shaders
- **Million-particle mode** — instanced rendering for massive simulations
- **WebXR / VR immersion** — step inside the cymatic field with hand controllers

---

## Project Philosophy

Cymatics Lab exists at the intersection of physics, art, music, and interaction. Sound creates order from chaos. Frequency shapes matter into geometry. This project makes that process visible, tangible, and explorable.

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

This project uses a **dual license** model:

**Free for non-commercial use** — personal projects, education, research, learning, and non-commercial open-source projects are all welcome. Modify it, share it, learn from it, create content with it.

**Commercial license required** — any use that generates revenue, is part of a paid product or service, or is deployed in a commercial context requires a separate license from Sentinel AI Systems.

See [LICENSE.md](LICENSE.md) for complete terms.

To discuss commercial licensing, contact Sentinel AI Systems via [GitHub](https://github.com/jkh2).
