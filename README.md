# Mandelbrot Explorer

An interactive, GPU-accelerated Mandelbrot set explorer that runs in your browser.

🔗 **[Live Demo](https://zack-fleischman-org.github.io/mandelbrot-explorer/)**

## Features

- **Fullscreen canvas** - Immersive visualization that fills your viewport
- **Pan and zoom** - Click and drag to pan, scroll wheel to zoom (supports touch on mobile)
- **WebGL rendering** - GPU-accelerated for smooth, real-time exploration
- **8 color schemes** - Classic, Fire, Ice, Electric, Rainbow, Ocean, Sunset, Monochrome
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
