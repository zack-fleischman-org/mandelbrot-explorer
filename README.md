# Mandelbrot Explorer

An interactive, GPU-accelerated Mandelbrot set explorer that runs in your browser.

🔗 **[Live Demo](https://zack-fleischman-org.github.io/mandelbrot-explorer/)**

## Features

- **Fullscreen canvas** - Immersive visualization that fills your viewport
- **Pan and zoom** - Click and drag to pan, scroll wheel to zoom (supports touch on mobile)
- **WebGL rendering** - GPU-accelerated for smooth, real-time exploration
- **Double-double precision** - Emulated 64-bit math on the GPU (~15 decimal digits) for deep zooms without pixelation
- **Smooth coloring** - Continuous escape-time coloring (toggleable) for banding-free gradients
- **Gradient editor** - Visually edit color stops, drag to reposition, click to add, double-click to remove
- **12 built-in color schemes** - Classic, Fire, Ice, Electric, Rainbow, Ocean, Sunset, Monochrome, Cosmic, Neon, Deep Ocean, Psychedelic
- **Save custom schemes** - Persist your own gradients to `localStorage` and reload them across sessions
- **Adjustable iterations** - From 50 to 2000 for detail vs. performance tradeoff
- **Location presets** - Jump to famous spots like Seahorse Valley, Elephant Valley, and more
- **Live coordinates** - See real/imaginary center and zoom level in real-time
- **Responsive design** - Works on desktop and mobile devices

## Usage

### Controls

| Action | Input |
|--------|-------|
| Pan | Click and drag (or touch drag on mobile) |
| Zoom | Scroll wheel (or pinch on mobile) |
| Toggle settings | Click ⚙️ button or press `S` key |

### Gradient Editor

| Action | Input |
|--------|-------|
| Add a color stop | Click anywhere on the gradient preview bar |
| Move a stop | Drag the round marker beneath the bar |
| Recolor a stop | Click the marker, then use the color picker |
| Delete a stop | Double-click the marker (or right-click) |
| Save current gradient | "Save Scheme…" button — names persist in `localStorage` |
| Delete saved scheme | Select it in the dropdown, then "Delete Scheme" |

### Location Presets

- **Seahorse Valley** - Classic spiral formations
- **Elephant Valley** - Elephant-like structures
- **Double Spiral** - Intricate spiraling patterns
- **Lightning** - Branching electric patterns
- **Starfish** - Star-shaped formations
- **Tendrils** - Delicate filament structures

## Running Locally

No build step required! Simply:

1. Clone the repository
2. Open `index.html` in a modern browser

Or serve with any static file server:

```bash
python -m http.server 8000
# Then open http://localhost:8000
```

## Deployment

This app is designed for GitHub Pages. Enable Pages in your repository settings and it will be live at `https://zack-fleischman-org.github.io/mandelbrot-explorer/`

## Technical Details

- Single HTML file with embedded CSS and JavaScript
- WebGL fragment shaders for GPU-accelerated computation
- **Double-double arithmetic in GLSL** — each complex coordinate is carried as a pair of `float`s `(hi, lo)` whose exact sum is the represented value. The shader implements `twoSum`, `fastTwoSum`, `twoProduct` (Veltkamp split, factor `2^12 + 1 = 4097` for the 24-bit float32 mantissa), and double-double `ddAdd` / `ddSub` / `ddMul`. JavaScript splits the center coordinate using `Math.fround` and sends `(cx_hi, cx_lo, cy_hi, cy_lo)` as a `vec4` uniform.
- **Gradient texture** — coloring is driven by a 256×1 RGBA texture built from the active gradient's color stops and sampled with `t` in the fragment shader, so any user-defined gradient renders at full GPU speed.
- No dependencies or build tools required
- Supports high-DPI displays (retina)

## Browser Support

Requires WebGL support. Works in all modern browsers:
- Chrome 9+
- Firefox 4+
- Safari 5.1+
- Edge 12+

## License

MIT
