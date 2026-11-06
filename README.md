# FourierFlower — Fourier Bloom 3D

![pic](pic.png)

A single-file interactive 3D Fourier-epicycle flower garden inspired by a nautilus spiral.

**[Open the live garden](https://anttiluode.github.io/FourierFlower/)**

## Run

Open `index.html` directly in Edge, Chrome, or Firefox. No dependencies, build tools, internet connection, or web server are needed. The included GitHub Pages workflow deploys the page automatically from `main`.

## Controls

- Drag the background to orbit the camera; scroll or pinch to zoom.
- Change harmonic layers, petal count, 3D depth, and animation speed.
- Toggle camera orbit, epicycle construction lines, and glowing particles.
- Replay the bloom, randomize the garden, pause motion, reset the camera, or save an image.

## How it works

Each flower is a sum of rotating complex exponentials:

```text
z(t) = Σ aₖ exp(i (nₖ t + φₖ))
```

The resulting curves are arranged along a three-dimensional logarithmic spiral. The renderer uses WebGL when initialization succeeds and otherwise creates a **new** canvas for the standalone software 3D renderer. This is essential because an existing WebGL canvas cannot be reused as a 2D canvas if a shader or other initialization step fails.

Original procedural interpretation; not an exact reproduction of George Savva’s source animation.
