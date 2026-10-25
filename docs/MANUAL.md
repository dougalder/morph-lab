# Morph Lab User Manual

## Table of Contents

1. [Getting Started](#getting-started)
2. [Single-Pair Mode](#single-pair-mode)
3. [Batch Sequence Mode](#batch-sequence-mode)
4. [Settings & Customization](#settings--customization)
5. [Exporting](#exporting)
6. [Advanced Techniques](#advanced-techniques)
7. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Opening the App

1. Navigate to `index.html` in your browser (or visit the live demo link)
2. You'll see two buttons: "Launch App (Recommended)" and "Safari Fallback"
3. Click "Launch App" to start

### The Interface

- **Header**: App title, theme toggle (light/dark), mode selector (Single Pair / Batch Sequence), Settings gear
- **Main Area**: Image panels, point markers, render button
- **Settings Popout**: Format and Export tabs (hidden until clicked)
- **View Tabs**: "start · end images" and "rendered" (rendered tab appears after render completes)

---

## Single-Pair Mode

Single-Pair mode morphs between two images smoothly.

### Step 1: Upload Images

1. Click **"START"** upload area → select a JPG or PNG file (recommended: 1000×1000 or larger)
2. Click **"END"** upload area → select your target image
3. Images are cropped to the selected aspect ratio (default: auto)

**Tips:**
- Use images of similar subject size (makes point marking easier)
- Faces work best with front-facing, well-lit photos
- Avoid extreme angles; the morphing works best with aligned poses

### Step 2: Adjust Crop (Optional)

If you want to zoom in or out before marking points:

1. Click **"crop"** under an image
2. Use the **zoom slider** (bottom of crop modal):
   - **Negative values** (left): zoom out (shrink image, add transparent padding)
   - **Positive values** (right): zoom in (crop tighter)
3. Drag the image preview to reposition the crop
4. Click **"apply"** to save

### Step 3: Mark Matching Points

1. **Click a point on the START image** (you'll see a red circle)
2. **Click the matching point on the END image** (you'll see a green circle)
3. A line connects them
4. Repeat until you have at least 4 pairs (8+ is better for smooth morphing)

**How to find matching points:**
- Eyes, nose, mouth corners
- Cheekbones, jaw, ears
- Hands, shoulders, major body landmarks
- Start with obvious features, then add detail points

**Adjusting points:**
- Drag any marked point to move it
- The line follows in real-time
- Both images share the same point indices (point #1 on Start = point #1 on End)

**Keyboard shortcuts:**
- **u**: Undo last point
- **c**: Clear all points
- **z**: Toggle point visibility

### Step 4: Optional—Auto Face Detection

For faster setup with faces:

1. Make sure "Face Mode" dropdown shows **"on"**
2. The app automatically detects ~40 facial landmarks on each image
3. Adjust any misaligned points by dragging
4. This is a **starting point**, not final—every point is fully editable

**Important:** Face detection works in Chrome/Edge only. Other browsers skip this step or show a notice.

### Step 5: Configure Export Settings

Click the **Settings gear** (top right) to open the popout:

#### Format Tab
- **Aspect Ratio**: Choose 1:1 (square), 16:9 (wide), 9:16 (tall), 4:3, 3:4, or auto
- This affects the crop area shown in both images
- Change at any time to re-crop

#### Export Tab
- **Hold per image**: How long each image displays (0–3 seconds, default: 2s)
- **Transition**: Morphing duration between images (0.5–8 seconds, default: 5s)
- **FPS**: Frame rate (12–30, default: 30)
  - Higher = smoother, larger file
  - 12–15 fps is fine for most uses
- **Format**: MP4 (lossy, universal) or WebM (lossless, alpha transparency)
  - Use **WebM** if you need transparent backgrounds
  - Use **MP4** if you need maximum compatibility

### Step 6: Render

1. Once both images are loaded, the **"render video"** button appears below the images
2. Click it
3. Watch the progress bar
4. When complete, the **"Rendered"** tab auto-appears and shows your output

### Step 7: Download

1. Click the download button or link in the Rendered tab
2. File name follows this format: `YYYY-MM-DD morph-lab-[aspect]-[resolution].[format]`
   - Example: `2026-10-24 morph-lab-1_1-480x480.mp4`
3. File saves to your Downloads folder

---

## Batch Sequence Mode

Batch mode morphs a series of images together smoothly.

### Step 1: Switch to Batch Sequence

1. Click **"Batch Sequence"** tab in the header
2. You'll see a drop zone and thumbnail strip

### Step 2: Upload Images

**Option A: Drag & Drop**
1. Drag a folder of images onto the drop zone
2. Images auto-sort by filename

**Option B: File Picker**
1. Click "choose folder" or "choose files" button
2. Select 2+ images

**Image Order:**
- Images are ordered by filename (alphabetical)
- **Naming convention:** prefix with numbers for predictable order
  - Good: `01-start.jpg`, `02-middle.jpg`, `03-end.jpg`
  - Avoid: `image1.jpg`, `image.jpg` (order may be unpredictable)

### Step 3: View Batch Info

- **Thumbnail strip** shows all loaded images
- **Count** displays: "3 / 3 images loaded"
- Click a thumbnail to jump to that transition

### Step 4: Set Transition Points

1. The app shows each **pair of consecutive images** (1→2, 2→3, etc.)
2. For each pair, mark matching points just like Single-Pair mode
3. **"copy from previous"** button copies points from the prior transition (handy for static backgrounds)
4. **"next"** / **"prev"** navigate between transitions

### Step 5: Export & Render

1. Configure settings in Settings → Export tab (same as Single-Pair)
2. Click **"render video"** when ready
3. The app morphs all consecutive pairs, blending them into one continuous video
4. Download as MP4, WebM, or PNG sequence

---

## Settings & Customization

### Opening Settings

Click the **gear icon** (⚙️) in the top-right corner. A popout appears with two tabs.

### Format Tab

| Setting | Range | Default | Notes |
|---------|-------|---------|-------|
| Aspect Ratio | auto, 1:1, 16:9, 9:16, 4:3, 3:4 | auto | Determines crop shape; can change anytime |

### Export Tab

| Setting | Range | Default | Notes |
|---------|-------|---------|-------|
| Hold per image | 0–3s | 2.0s | Static display time before morph begins |
| Transition | 0.5–8s | 5.0s | Duration of the morphing animation |
| FPS | 12–30 | 30 | Frames per second (higher = smoother, larger file) |
| Format | MP4, WebM | MP4 | MP4: universal; WebM: transparency |

### Theme

Click the **theme toggle** (🌙 or ☀️) in the header to switch light/dark mode. Your choice is saved automatically.

### Clearing Data

- **Clear all points**: Click the "clear" button in the points row
- **Remove an image**: Click "replace image" to upload a new one
- **Reset everything**: Reload the page

---

## Exporting

### MP4 Format

**Best for:** Social media, video players, compatibility
- **Pros:** Universal support, smaller file size, embeddable
- **Cons:** Opaque (no transparency), lossy compression
- **Use case:** YouTube, Instagram, presentations

### WebM Format

**Best for:** Compositing, transparency, advanced editing
- **Pros:** Lossless compression, preserves alpha channel, excellent for overlays
- **Cons:** Limited player support, larger file
- **Use case:** After Effects, compositing, visual effects

### PNG Sequence

**Best for:** Frame-by-frame control, visual effects, high-quality preservation
- **Output:** ZIP file containing numbered PNG images (e.g., `001.png`, `002.png`, …)
- **Use case:**
  - Manually edit individual frames in Photoshop
  - Assemble with custom effects using ffmpeg
  - Ultra-high quality (no compression loss)
  - Compositing in After Effects or Nuke

**Converting PNG sequence to video (via ffmpeg):**
```bash
ffmpeg -framerate 30 -i frame_%03d.png -c:v libx264 -crf 18 output.mp4
```

---

## Advanced Techniques

### Making Smooth Morphs

**Key principles:**
1. **More points = smoother transition**
   - 4 points: basic shapes
   - 8+ points: smooth transitions
   - 16+ points: very fine detail

2. **Point placement strategy**
   - Start with major landmarks (eyes, nose, mouth)
   - Add points along edges (jawline, hair)
   - Fill in gaps (forehead, cheeks)
   - Avoid clustered points; spread them out

3. **Matching accuracy**
   - Each start point should correspond to the same feature on the end image
   - Slight misalignments will cause "wobble"—fix by dragging

### Batch Morphing Tips

- **Static backgrounds:** Use "copy from previous" to reuse background points
- **Multiple subjects:** Mark each character separately (more points overall)
- **Consistent lighting:** Images with similar exposure blend better
- **Pose progression:** Gradual pose changes (frame-by-frame) look more natural than extreme jumps

### Performance Optimization

- **Reduce resolution:** Lower FPS or aspect ratio for faster renders
- **Shorter duration:** Fewer frames = faster render
- **Fewer points:** Simplifies triangulation (but may look less smooth)
- **Batch mode:** Rendering 10 images is faster than 10 separate single-pair renders

### Creating Loops

1. Render the morph (A → B)
2. Manually reverse the video or create a second render (B → A)
3. Concatenate: A → B → A
4. Use `ffmpeg`:
   ```bash
   ffmpeg -i part1.mp4 -i part2.mp4 -filter_complex "[0][1]concat=n=2:v=1:a=0" -c:v libx264 loop.mp4
   ```

---

## Troubleshooting

### General Issues

#### The app won't load
- **Check browser:** Use Chrome, Edge, Firefox, or Safari (latest versions)
- **Clear cache:** Ctrl+Shift+Delete (or Cmd+Shift+Delete on Mac), clear cache, reload
- **Try fallback:** Click "Safari Fallback" from index.html

#### "WebGL not supported" error
- Your browser doesn't support WebGL
- **Solution:** Use `morph-lab-safari.html` (Canvas2D rendering is slower but works)
- Or update to a modern browser version

#### Images won't upload
- **Check file:** Must be JPG or PNG, < 50MB
- **Try different image:** Occasionally a corrupted file fails silently
- **Check browser console:** Press F12 → Console tab for error messages

#### Settings/theme not saving
- **Check storage:** Browser may have blocked local storage
- **Fix:** Allow "local storage" in browser permissions
- **Reload:** Reset happens on page reload

### Point Marking Issues

#### Points disappear or move unexpectedly
- **Zoom too high:** Click "crop" and reduce zoom slider
- **Browser memory low:** Close other tabs; restart browser
- **Accidental drag:** Make sure you're clicking, not dragging

#### Face detection points are way off
- **Poor lighting:** Works best with clear, even lighting
- **Wrong angle:** Face should be front-facing
- **Partial faces:** Ensure full face is visible
- **Fix:** Manually drag incorrect points, or disable and mark manually

#### One image won't crop properly
- **Aspect locked:** Aspect ratio is locked; all images crop to the same shape
- **Fix:** Change aspect ratio in Settings → Format, or change before uploading

### Rendering Issues

#### Render is very slow
- **High resolution:** Reduce FPS (try 12 instead of 30)
- **Long duration:** Reduce hold time or transition seconds
- **Many points:** Simplify to 8–12 points instead of 30+
- **Large image:** Crop to smaller resolution
- **Browser overloaded:** Close other tabs; browser uses main thread

#### Render finished but video won't play
- **Wrong format:** Some players don't support WebM
- **Try MP4 instead:** MP4 is universally supported
- **Check file size:** 0 bytes = error during render; try with fewer points/lower resolution

#### Can't download file
- **Check browser:** Some older browsers have download issues
- **Try different browser:** Test in Chrome/Firefox/Safari
- **Check downloads folder:** File may have saved with a different name
- **Storage full:** Ensure drive has space

### Face Detection Issues

#### Face detection slow/hangs
- **Large image:** Face detection is slower on high-res images (> 1000×1000)
- **Multiple faces:** The detector gets confused; hide other faces or use manual marking
- **Browser overloaded:** Close other tabs

#### Face detection not available (message says "Chrome/Edge only")
- **Browser limitation:** TensorFlow.js + Face API not available in other browsers
- **Solution:** Mark points manually (often faster anyway)

#### Face points badly misaligned
- **Unusual pose:** Side-profile or tilted faces confuse the detector
- **Solution:** Fix manually by dragging (each point is fully editable)

### Batch Mode Issues

#### Images in wrong order
- **Filename sort:** Images sort alphabetically by filename
- **Fix:** Rename files with numbers: `01-intro.jpg`, `02-middle.jpg`, `03-end.jpg`

#### Can't select a folder
- **Browser limitation:** Some browsers don't support folder selection
- **Workaround:** Click "choose files" and manually select each image in order

#### "transition 1 of 2" takes too long to load
- **Large image set:** 20+ images slows down UI
- **Reduce resolution:** Downsize images before uploading
- **Use single-pair instead:** Render smaller batches separately and concatenate

---

## Tips & Tricks

### For Best Results

1. **Lighting:** Similar lighting in both images = cleaner morph
2. **Focus distance:** Keep subjects at similar distances from camera
3. **Backgrounds:** Morphing works on everything (background too!); solid backgrounds are easier
4. **Color space:** Both images should use same color profile (usually sRGB)

### Time Estimates

- **Marking points:** 2–5 minutes per pair (depending on detail)
- **Rendering:** 
  - 480×480, 5 seconds, 30fps: ~2–3 seconds
  - 720×720, 10 seconds, 30fps: ~5–8 seconds
  - High-res, batch, many points: up to 30+ seconds

### Keyboard Shortcuts (in point-marking view)

| Key | Action |
|-----|--------|
| **u** | Undo last point |
| **c** | Clear all points |
| **z** | Toggle point visibility |
| **Esc** | Close crop modal (if open) |

---

## Glossary

| Term | Definition |
|------|-----------|
| **Morph** | Smooth transition between two images using point-based animation |
| **Delaunay Triangulation** | Math technique to create smooth mesh from points |
| **Point pair** | Start point (on left image) + End point (on right image) |
| **Aspect ratio** | Shape of image (1:1 = square, 16:9 = wide, etc.) |
| **Transition** | Duration of the morphing animation |
| **Hold time** | How long each image displays before morphing |
| **FPS** | Frames per second; higher = smoother video |
| **Alpha** | Transparency channel in images |
| **Batch sequence** | Multiple images morphed in order (A→B→C→D) |

---

## Contact & Support

- **Report bugs:** [GitHub Issues](https://github.com/yourusername/morph-lab/issues)
- **Feature requests:** Same link
- **Questions:** Check [README.md](../README.md) first

---

**Last updated:** October 24, 2026  
**App version:** 2.0 (redesigned UI with Settings popout and view tabs)
