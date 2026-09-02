# Three.js Web3D Annotation Test

Minimal browser test for engineering-style annotation in real 3D world space.

## Features

- Three.js 3D scene
- OrbitControls
- Raycaster surface picking
- Pick two 3D points to measure
- 3D dimension line
- Extension lines
- 3D arrowheads
- Distance calculation in metres and millimetres
- CSS2D text label anchored to the 3D dimension
- Multiple dimensions
- Clear annotations

## Test

Open `index.html` through a local HTTP server or enable GitHub Pages for the repository root.

Example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Architecture

`Raycaster -> World-space points -> Dimension geometry -> CSS2D annotation`

The geometry (dimension lines and arrows) lives in Three.js world space. The text is screen-readable HTML anchored to a 3D world position using CSS2DRenderer.
