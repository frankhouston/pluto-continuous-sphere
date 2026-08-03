# Pluto – Continuous Sphere

A transmorphic 3D visualization of Pluto projected onto a globe, featuring procedural
fractal interpolation for the southern hemisphere, texture switching, and an animated
APNG showing two full rotations.

## Animated Preview

![Pluto – two full rotations](https://github.com/frankhouston/pluto-continuous-sphere/releases/download/pluto-is-a-planet/pluto_two_rotations_apng.png)

> **960×540 · 10fps · 12.6s · 2 rotations · Pluto only (no GUI) — [Download full 42.7MB APNG](https://github.com/frankhouston/pluto-continuous-sphere/releases/download/pluto-is-a-planet/pluto_two_rotations_apng.png)**

## Features

- **Real Blue-Marble texture** with enhanced ChatGPT-generated color map
- **Fractal southern hemisphere** — multi-scale noise seeded from northern palette,
  matching New Horizons statistics (mean altitude -1.6km, RMS roughness 0.72km)
- **Topographic bump mapping** for mountain relief
- **Atmospheric glow** and starfield background
- **Transmorphic UI** — panel morphs on hover with cyan glow, subheading animates in
- **"Make Pluto Great Again"** subheading that fades in during interaction
- **Texture switch button** — cycle through 3 textures: Blue-Marble, Planet IX #1, Planet IX #2
- **Orbit/zoom controls** — drag to rotate, scroll to zoom
- **Author credit**: Frank Houston — Planet IX Discovered (Pluto found by Tombaugh, 1930)

## Files

| File | Description |
|---|---|
| `pluto_continuous_demo.html` | Main interactive demo (single-file, Three.js r128 via CDN) |
| `pluto_texture_alt.png` | Alternate texture #1 for switch button |
| `pluto_texture_alt2.png` | Alternate texture #2 for switch button |
| `capture_pluto_apng.js` | Puppeteer + ffmpeg APNG capture script |
| `enhanced_pluto_color.png` | Extracted color texture map |
| `enhanced_pluto_bump.png` | Extracted bump map |
| `enhanced_pluto_critical_data.json` | Critical parameters and code extraction |
| `pluto_two_rotations_apng.png` | Animated PNG (2 rotations, 42.7MB) — download from [GitHub Release](https://github.com/frankhouston/pluto-continuous-sphere/releases) |

## Usage

### Interactive Demo

```bash
# Start a local server
npx serve . -p 8399

# Open http://localhost:8399/pluto_continuous_demo.html
```

### Capture Animated PNG

```bash
npm install puppeteer  # one-time setup
node capture_pluto_apng.js
```

The capture script starts a local HTTP server, launches headless Chrome with
SwiftShader WebGL, hides the UI for a clean Pluto-only capture, and combines
frames into an APNG via ffmpeg.

## Technical Details

- **Resolution**: 960×540 (540p)
- **Frame rate**: 10fps
- **Duration**: ~12.6 seconds (2 full rotations at max speed)
- **Encoding**: APNG (lossless RGBA, paeth predictor, infinite loop)

## Author

**Frank Houston** — Planet IX Discovered

Pluto (a.k.a. Planet IX) was discovered by [Clyde Tombaugh](https://en.wikipedia.org/wiki/Clyde_Tombaugh)
at Lowell Observatory, 1930.
