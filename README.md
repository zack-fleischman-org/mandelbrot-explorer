# Mandelbrot Explorer

An interactive, high-precision Mandelbrot set explorer that runs in your browser with infinite zoom capabilities.

🔗 **[Live Demo](https://zack-fleischman-org.github.io/mandelbrot-explorer/)**

## Features

- **Fullscreen canvas** - Immersive visualization that fills your viewport
- **Pan and zoom** - Click and drag to pan, scroll wheel to zoom (supports touch on mobile)
- **Infinite precision zoom** - Smooth zoom past 1e20 using arbitrary-precision arithmetic
- **8 color schemes** - Classic, Fire, Ice, Electric, Rainbow, Ocean, Sunset, Monochrome
- **Adjustable iterations** - From 50 to 2000 for detail vs. performance tradeoff
- **Location presets** - Jump to famous spots like Seahorse Valley, Elephant Valley, and more
- **High-precision coordinates** - See center location with 20+ significant figures
- **Progressive rendering** - Fast interaction feedback with full-quality rendering when idle
- **Responsive design** - Works on desktop and mobile devices

## Usage

### Controls

| Action | Input |
|--------|-------|
| Pan | Click and drag (or touch drag on mobile) |
| Zoom | Scroll wheel (or pinch on mobile) |
| Toggle settings | Click ⚙️ button or press `S` key |

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

## Precision Upgrade

This explorer now uses arbitrary-precision arithmetic (via Decimal.js with 60-digit precision) to enable smooth zoom past 1e20. The classic WebGL float precision limit (~7 significant digits) no longer applies. Coordinates are displayed with 20+ significant figures so you can see exactly where you are in the fractal.

## Technical Details

- Single HTML file with embedded CSS and JavaScript
- Canvas 2D rendering with arbitrary-precision Mandelbrot computation
- Embedded Decimal.js library for 60-digit precision arithmetic
- Progressive rendering: reduced resolution during interaction, full quality when idle
- No dependencies or build tools required
- Supports high-DPI displays (retina)

## Browser Support

Works in all modern browsers with Canvas 2D support:
- Chrome 9+
- Firefox 4+
- Safari 5.1+
- Edge 12+

## License

MIT
