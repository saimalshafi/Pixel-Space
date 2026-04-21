# Pixel Space

A spatial exploration of digital images. Upload a photo and view it as a point cloud in three color spaces:

- **Image** — pixels in screen-space with configurable depth (brightness, R, G, B, or edges)
- **RGB Linear** — particles positioned by their linear RGB values (true sRGB → linear conversion)
- **HSV** — cylindrical mapping: hue = angle, saturation = radius, value = height

Single-file web app. No build step, no backend. Drop an image, adjust the controls.

## Running locally

Open `index.html` in a modern browser (Chrome, Safari, Firefox, Edge).
It loads Three.js from a CDN, so you'll need internet the first time.

## Features

- Drag-and-drop image upload
- Three color space projections with smooth transitions
- Depth modes: brightness (Rec. 709 luma), R/G/B channel, Sobel edges
- Color palette extraction (k-means) — click a swatch to isolate similar pixels
- Hue / brightness / contrast / palette-size adjustments
- Auto-rotation, idle motion, cursor pull
- PNG export (2× supersampled) and 1280×1280 video export (.mov/H.264 where supported)

## Stack

- [Three.js](https://threejs.org/) r160 via ESM import map
- Vanilla JS / CSS, no framework
- WebGL point cloud shader with per-particle color, alpha, and spring physics
