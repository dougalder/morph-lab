# Morph Lab 🌀

A powerful, browser-based image morphing tool that creates smooth transitions between two images. Everything runs locally in your browser—no server uploads, no external dependencies.

## Features

✨ **Core Capabilities**
- Mark matching points between start and end images
- Automatic face detection (optional, Chrome/Edge only)
- Smooth morphing animation with Delaunay triangulation
- Real-time preview and precise point adjustment
- Support for both single-pair and batch sequence morphing

📹 **Export Options**
- MP4 video (universal compatibility)
- WebM video (with real alpha/transparency support)
- PNG sequence (for advanced compositing in After Effects, ffmpeg, etc.)

🎨 **Customization**
- 6 aspect ratio presets (auto, 1:1, 16:9, 9:16, 4:3, 3:4)
- Adjustable hold time per image (0–3 seconds)
- Transition duration (0.5–8 seconds)
- Frame rate control (12–30 fps)
- Light & dark mode

🌐 **Browser Support**
- Chrome & Edge (WebGL, full performance)
- Firefox (WebGL)
- Safari (Canvas2D fallback for compatibility)
- Any modern browser with ES2020 support

## Getting Started

### Option 1: Visit Online
Simply open `index.html` in a modern web browser.

### Option 2: Run Locally
```bash
# Clone the repository
git clone https://github.com/yourusername/morph-lab.git
cd morph-lab

# No build step required—just open index.html in your browser
# Or use a local web server:
python -m http.server 8000
# Then visit http://localhost:8000
```

## Usage

1. **Upload Images**
   - Click "Upload" to select a start and end image (JPG or PNG)
   - Images are stored in browser memory—nothing is sent to a server

2. **Mark Points** (Single Pair Mode)
   - Click on the start image to place a point
   - Click the matching location on the end image
   - Drag any point to adjust
   - At least 4 points are recommended; more points = smoother transitions

3. **Optional: Auto Face Detection**
   - Enable "Face Mode" to automatically detect ~40 facial landmarks
   - Points are still fully draggable afterward (it's a starting point, not final)
   - Chrome/Edge only

4. **Adjust Settings**
   - Open Settings (gear icon) to change aspect ratio, hold time, transition speed, FPS
   - Format tab: choose aspect ratio before uploading
   - Export tab: configure video quality and timing

5. **Render**
   - Click "render video" when images are loaded
   - Watch the progress bar and preview the result
   - Switch to "Rendered" tab when complete

6. **Export**
   - Download MP4 (plays anywhere)
   - Download WebM (preserves transparency)
   - Export PNG sequence for frame-by-frame control

## Batch Mode

For morphing image sequences (3+ images):

1. Click "Batch Sequence" tab
2. Drop a folder of images (ordered by filename)
3. Set transition points between consecutive pairs
4. Render and export as above

## Technical Details

### Technologies Used
- **D3.js**: Delaunay triangulation for smooth point-based morphing
- **Canvas & WebGL**: Image rendering and video composition
- **MediaRecorder API**: Real-time video encoding (MP4, WebM)
- **JSZip**: PNG sequence bundling into downloadable ZIP
- **TensorFlow.js + Face API**: Optional facial landmark detection (Chrome/Edge)

### Architecture
- Single-file HTML application (no build process required)
- Two versions: WebGL (morph-lab.html) and Canvas2D fallback (morph-lab-safari.html)
- All computation happens in your browser; no network requests
- Automatic theme detection (respects OS dark mode preference)

### File Format
Exported files follow this naming convention:
```
YYYY-MM-DD [morph-lab]-[AspectRatio]-[Resolution].[format]
Example: 2026-10-24 morph-lab-1_1-480x480.mp4
```

## Preferences & Customization

The app respects your browser preferences:
- **Light/Dark Mode**: Toggle in header, syncs with OS theme
- **Settings Tab**: Last selected tab is remembered
- **Panel State**: UI state persists across sessions

## Troubleshooting

**"WebGL not supported" error?**
- Use `morph-lab-safari.html` (Canvas2D fallback)
- Update your browser to a recent version

**Video export takes too long?**
- Reduce FPS (default 30 → try 12–24)
- Reduce resolution (lower aspect ratio or crop tighter)
- Shorter duration reduces frame count

**Face detection not working?**
- Face detection is Chrome/Edge only
- Requires network access to load TensorFlow.js models (proxy-friendly)
- Run on localhost if behind a corporate proxy

**Points not staying where I placed them?**
- Make sure you're clicking on the canvas, not dragging
- Try resetting with the "clear" button and re-marking

## Known Limitations

- Face detection: Chrome/Edge browsers only
- Maximum image size: ~4K (browser memory limits)
- Face detection reliability: best with clear, front-facing faces
- MP4 exports: transparent areas render as black (use WebM for alpha preservation)

## Performance Notes

- **Smooth morphing** requires at least 4 matched points (8+ recommended)
- **Render time** depends on: duration, FPS, resolution
  - Example: 5-second 480×480 at 30fps ≈ 2–5 seconds to render
- **Large image sequences** (20+ images) may slow down the batch UI

## Privacy

✅ **100% Private**
- No data leaves your computer
- No account required
- Images never uploaded to any server
- Browser storage is local only
- Works entirely offline (except optional face detection models)

## License

This project is licensed under the MIT License—see `LICENSE` file for details.

### Third-Party Licenses

This project includes or uses the following open-source libraries:

- **D3.js** (v7.9.0): Copyright (c) 2010–2021, Mike Bostock. Licensed under ISC.
- **Face API (face-api.js)**: Licensed under MIT.
- **TensorFlow.js**: Licensed under Apache 2.0.
- **JSZip**: Licensed under MIT/GPLv3.

See `ATTRIBUTION.md` for full attribution and links.

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## Roadmap

- [ ] Perspective warping (advanced control points)
- [ ] GPU-accelerated Delaunay triangulation
- [ ] More format support (GIF, APNG)
- [ ] Reverse/loop export options
- [ ] Undo/redo history
- [ ] Keyboard shortcuts
- [ ] Color space conversions (working color space selection)

## Support

Found a bug or have a feature request? [Open an issue](https://github.com/yourusername/morph-lab/issues).

---

Made with ❤️ • [Visit Live Demo](https://yourusername.github.io/morph-lab) • [Report Issues](https://github.com/yourusername/morph-lab/issues)
