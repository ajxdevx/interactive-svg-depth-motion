# Interactive SVG Depth Motion

An interactive hero section where stacked SVG-masked layers follow the cursor with staggered, smoothed motion to create a parallax depth effect.

**Author:** AJ

## Preview

Move your cursor over the hero area to see each depth layer respond with a slight delay, giving the surface a 3D feel without WebGL or 3D transforms.

## Tech stack

- HTML & CSS (SVG masks, layered composition)
- JavaScript
- [GSAP](https://gsap.com/) for the animation loop
- [Vite](https://vitejs.dev/) for local development

## Getting started

```bash
npm install
npm run dev
```

Then open the URL shown in your terminal (usually `http://localhost:5173`).

## Project structure

```
├── index.html      # Hero markup and depth layers
├── styles.css      # Layout, masks, and responsive styles
├── script.js       # Cursor tracking and staggered layer motion
└── public/
    ├── mask.svg    # SVG mask used by each depth layer
    └── logo.png    # Center logo image
```

## How it works

1. Several `.depth-layer` elements are stacked on top of each other.
2. Each layer uses an SVG mask cutout via CSS `mask` / `-webkit-mask`.
3. Mouse position is tracked and stored in a short trail buffer.
4. Each layer reads from a different point in that trail, creating staggered movement.
5. GSAP's ticker applies smooth interpolation (`lerp`) on every frame.

## License

ISC
