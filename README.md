# Cymatics Lab

### Interactive Particle Resonance & Gesture Simulator — Sentinel Edition v2.2

Cymatics Lab is a high-performance, browser-based particle simulator that visualizes resonance, harmonic interference, and dynamic flow fields in real time. Upload your own music and watch the cymatic field dance to the audio, sculpt particle motion with hand gestures, or explore scientifically-inspired frequency patterns from Chladni plates to toroidal resonance.

The entire application runs in a **single HTML file** with a **WebGL rendering engine**. No build process, no backend, no dependencies to install. Host it directly on GitHub Pages.

> **A collaboration between [Sentinel AI Systems](https://github.com/jkh2) and Claude Sentinel — built under the SIDLF (Symbiotic Intelligent Digital Life Forms) framework.**

---

## Live Demo

**[Launch Cymatics Lab](https://jkh2.github.io/Sentinel-Cymatics-Lab/)**

Open the page and begin interacting immediately.

---

## What You'll See

Particles organize themselves into standing-wave patterns driven by frequency, harmonic ratios, and interference fields. The result looks like vibrating sand on a Chladni plate — except you can reach in and sculpt it with your hands, let your music drive the experience, or explore real physics equations that produce stunning geometric patterns.

Switch to Chladni Plate mode and sweep through frequencies — you'll see real eigenmode shapes emerge as the plate's vibration modes change. Switch to Toroidal Resonance and watch particles orbit a torus ring with angular interference patterns. Drop in a bass-heavy track and watch the field pulse with every beat. Every pattern is different. Every interaction reshapes what you see.

---

## Features

### Music-Reactive Visualization

Upload any audio file or connect your microphone and watch the cymatic field respond to real audio in real time.

- **File upload** — load MP3, WAV, OGG, or any browser-supported audio format with full transport controls (play, pause, stop, seek, volume)
- **Microphone input** — analyze live audio from your mic without feedback
- **Real-time FFT analysis** — 256 frequency bins split into bass, mids, and highs, smoothed for fluid visual response
- **Band-mapped reactivity** — bass drives field strength and frequency, mids morph pattern geometry and modulation, highs sharpen nodal detail
- **Adjustable reactivity slider** — from subtle ambient response to dramatic beat-driven visuals
- **Beat detection** — monitors bass energy spikes and triggers bloom events on every beat
- **Live spectrum visualizer** — real-time frequency bars color-coded by band with percentage readouts

### Physics-Based Cymatic Modes *(New in v2.2)*

Eight simulation presets, including three new scientifically-inspired modes:

| Preset | Description |
|--------|-------------|
| **Cymatics** | Dual-frequency interference field with radial harmonics — the original artistic mode |
| **Chladni Plate** | Real eigenmode equation: cos(nπx)sin(mπy) + sin(nπx)cos(mπy). Mode numbers derive from frequency — higher frequencies produce more complex nodal geometry |
| **Radial Standing Wave** | Concentric ring patterns from sin(r·freq - time) with angular harmonics controlled by the harmonic ratio |
| **Toroidal Resonance** | Particles orbit a torus ring shape with angular and poloidal interference modes — like looking down at a vibrating donut |
| **Galaxy** | Spiral arm dynamics with gravitational pull |
| **Vortex** | Tight rotational pull with radial compression |
| **Wave Field** | Flowing wave interference patterns |
| **Orbitals** | Multi-lobed orbital motion with band structure |

### Curl Noise Flow Field *(New in v2.2)*

All presets now include organic rotational flow via curl noise — a divergence-free vector field that produces smooth, fluid-like particle motion. In cymatics modes, curl noise activates between nodal lines, keeping the nodes crisp while the interstitial space flows like plasma. Non-cymatics presets get organic turbulence layered on top of their existing dynamics.

### Pattern Sharing via URL *(New in v2.2)*

Hit **Share Link** in the Cymatics tab to generate a shareable URL that encodes your exact configuration — preset, frequency, harmonic ratio, modulation, field strength, sharpness, and theme. Send the link to anyone and they'll see your exact pattern when they open it.

Example: `https://jkh2.github.io/Sentinel-Cymatics-Lab/?p=BASE64CODE`

### Session Recording

Record your session as a video file with synchronized audio.

- **One-click recording** — hit Record in the Sim tab to start, hit again to stop and auto-download
- **Audio capture** — automatically merges music playback or oscillator audio with the video
- **Pulsing REC indicator** with running timer
- **WebM output** at 5 Mbps, 30fps — plays in Chrome, Firefox, VLC, and most modern players

### WebGL Particle Engine

The renderer uses WebGL point sprites with custom GLSL shaders for soft glowing particles, HSV color mapping on the GPU, and additive blending with a ring-buffer trail system.

- Up to 50,000 simultaneous particles
- Full clear every frame with ring-buffer trail echoes — no brightness accumulation
- Adaptive startup tuning based on device capability (mobile ~5k, laptop ~8k, desktop ~20k)
- Smooth 60fps on modern hardware

### Cymatic Frequency Presets

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

**Precise frequency control:** slider with 0.1 Hz resolution plus a numeric input field for typing exact Hz values.

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

### Dual-Oscillator Audio

Enable the built-in audio engine to hear cymatic frequencies. Two oscillators — base frequency and harmonic — with support for sine, triangle, square, and sawtooth waveforms.

### Visual Themes

Six visual themes: **Midnight**, **Aurora**, **Ember**, **Void**, **Solar**, **Deep Sea**. Additional controls for additive glow, bloom intensity, color saturation, and hue rotation speed.

### Random Bloom

Generate a completely new cymatic structure instantly by randomizing all harmonic parameters with a visual bloom transition.

---

## How It Works

Particles move through a composite force field:

```
totalForce = cymaticField + curlNoiseFlow + gestureField + pointerField + harmonicModulation + fftReactivity
```

### Cymatics Mode

The field uses dual-frequency interference with radial harmonics. Particles migrate toward nodal lines where the wave interference crosses zero.

### Chladni Plate Mode

Uses the real Chladni plate eigenmode equation. Mode numbers (n, m) are derived from the frequency and harmonic ratio controls, so changing frequency actually changes which vibration mode of the plate you're seeing.

### Curl Noise

A divergence-free vector field computed via central differencing of a noise function. The curl operation produces smooth rotational flow without sources or sinks — particles swirl organically without clumping or dispersing.

### Music Reactivity

A real-time FFT analyser splits 256 frequency bins into bass/mid/high bands, smooths the values, and maps them to cymatic parameters each frame. Beat detection monitors bass energy spikes and triggers visual bloom events.

### Rendering

WebGL point sprites with per-particle hue, alpha, and size attributes. A ring buffer stores the last 6 frames of particle positions to render trail echoes. The framebuffer is fully cleared every frame — no brightness accumulation.

---

## Controls

The UI is organized into five tabbed panels:

### Sim Tab
| Control | Function |
|---------|----------|
| Pause / Play | Toggle simulation |
| Reset | Reinitialize particles and clear screen |
| Audio On/Off | Toggle built-in oscillator |
| Fullscreen | Enter/exit fullscreen mode |
| Record | Start/stop session video recording |
| Preset selector | 8 simulation modes including Chladni, Radial, Toroidal |
| Waveform selector | Sine, Triangle, Square, Sawtooth |
| Particles | Particle count (2k–50k) |
| Speed | Simulation time scale |
| Particle Size | Point sprite radius |
| Drag | Velocity damping |
| Pointer Force | Mouse/touch influence strength |
| Trail Length | Trail echo visibility |

### Cymatics Tab
| Control | Function |
|---------|----------|
| Next Frequency | Cycle through 15 frequency presets |
| Random Bloom | Randomize all harmonic parameters |
| Capture | Export current config as base64 |
| Share Link | Copy a shareable URL to clipboard |
| Base Frequency | Primary wave frequency (20–2000 Hz) with numeric input |
| Harmonic Ratio | Secondary frequency multiplier |
| Modulation Rate / Depth | Frequency modulation controls |
| Pattern Scale | Spatial frequency scaling |
| Field Strength | Force field magnitude |
| Nodal Sharpness | How tightly particles cluster at nodes |

### Music Tab
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
| Bloom Effect / Intensity | Bloom rendering controls |
| Color Saturation | HSV saturation level |
| Hue Rotation Speed | Rate of color cycling |

---

## Installation

```bash
git clone https://github.com/jkh2/Sentinel-Cymatics-Lab.git
cd Sentinel-Cymatics-Lab
open index.html
```

No build process. No npm install. No server. Just a browser.

---

## Deploying to GitHub Pages

1. Push the repository to GitHub
2. Go to **Settings → Pages**
3. Select **Deploy from main branch**
4. Live at **https://jkh2.github.io/Sentinel-Cymatics-Lab/**

---

## Technologies

| Technology | Purpose |
|------------|---------|
| WebGL | GPU-accelerated particle rendering via point sprites |
| GLSL | Custom vertex and fragment shaders for glow effects |
| JavaScript | Physics simulation, curl noise, FFT analysis, gesture processing |
| Web Audio API | FFT analyser, dual-oscillator synthesis, music playback |
| MediaPipe Hands | Real-time hand landmark detection via webcam |
| MediaRecorder API | Session video recording with audio capture |
| HTML5 | Single-file application container |

Everything runs client-side. Zero backend. Zero build tools.

---

## Performance

| Device | Default Particles | Expected FPS |
|--------|-------------------|-------------|
| Mobile | ~5,000 | 30–60 |
| Laptop | ~8,000 | 60 |
| Desktop | ~12,000–20,000 | 60 |

---

## Roadmap

Planned upgrades for future versions:

- **3D particle field with orbit camera** — particles in xyz space with mouse/touch rotation and zoom
- **Two-hand gesture control** — left hand rotates view, right hand sculpts the field
- **AI music analysis** — intelligent auto-selection of cymatic parameters based on track characteristics
- **Conversational AI control** — natural language commands to shape the visualization
- **AI pattern recognition** — describes emergent geometry and identifies harmonic modes
- **AI autonomous composition** — generates evolving cymatic sequences over time
- **GPU compute particle physics** — move force calculations to compute shaders
- **Million-particle mode** — instanced rendering for massive simulations
- **WebXR / VR immersion** — step inside the cymatic field with hand controllers

---

## Project Philosophy

Cymatics Lab exists at the intersection of physics, art, music, and interaction. Sound creates order from chaos. Frequency shapes matter into geometry. This project makes that process visible, tangible, and explorable.

The focus is **visual beauty first**, with optional deeper exploration of the physical behavior underneath — from artistic interference patterns to real Chladni plate eigenmodes.

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

The Solfeggio frequency presets draw from historical and contemporary interest in specific frequencies and their relationship to harmonic structure. The Chladni plate equations reference the foundational work of **Ernst Chladni** in acoustic physics.

---

## License

This project uses a **dual license** model:

**Free for non-commercial use** — personal projects, education, research, learning, and non-commercial open-source projects are all welcome. Modify it, share it, learn from it, create content with it.

**Commercial license required** — any use that generates revenue, is part of a paid product or service, or is deployed in a commercial context requires a separate license from Sentinel AI Systems.

See [LICENSE.md](LICENSE.md) for complete terms.

To discuss commercial licensing, contact Sentinel AI Systems via [GitHub](https://github.com/jkh2).
