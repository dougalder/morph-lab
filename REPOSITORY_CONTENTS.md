# Repository Contents

This file describes all files included in the Morph Lab GitHub repository.

## Quick Reference

```
morph-lab/
│
├── 📄 ROOT FILES
│   ├── index.html                    Landing page & app launcher
│   ├── morph-lab.html               Main app (WebGL, recommended)
│   ├── morph-lab-safari.html        Fallback version (Canvas2D for Safari)
│   ├── README.md                    Project overview & getting started
│   ├── LICENSE                      MIT License (project)
│   ├── ATTRIBUTION.md               Third-party library licenses
│   ├── CONTRIBUTING.md              Contribution guidelines
│   ├── .gitignore                   Git ignore rules
│   └── REPOSITORY_CONTENTS.md       This file
│
├── 📁 docs/
│   ├── MANUAL.md                    User guide with detailed instructions
│   └── SCREENSHOTS.md               Screenshot descriptions
│
└── 📁 screenshots/
    ├── 01-landing-page.png          Landing page overview
    ├── 02-main-app-light.png        Main interface (light theme)
    ├── 03-main-app-dark.png         Main interface (dark theme)
    ├── 04-settings-format.png       Settings popout (format tab)
    ├── 05-settings-export.png       Settings popout (export tab)
    └── 06-batch-mode.png            Batch sequence mode
```

---

## File Descriptions

### Root Files

#### **index.html**
- **Purpose:** Landing page and app launcher
- **Size:** ~12 KB
- **Content:**
  - Feature overview
  - Launch buttons (WebGL & fallback)
  - Links to documentation
- **No external dependencies** (pure HTML/CSS)

#### **morph-lab.html**
- **Purpose:** Main Morph Lab application
- **Size:** ~127 KB
- **Technologies:** WebGL, Canvas, MediaRecorder API
- **Features:**
  - Single-pair morphing
  - Batch sequence support
  - Automatic face detection (optional)
  - MP4, WebM, PNG sequence export
  - Light & dark mode
- **Browser Support:** Chrome, Edge, Firefox (WebGL required)
- **External Dependencies:** D3.js, TensorFlow.js, Face API (loaded from CDN)

#### **morph-lab-safari.html**
- **Purpose:** Fallback version for Safari and non-WebGL browsers
- **Size:** ~121 KB
- **Key Difference:** Canvas2D rendering instead of WebGL
- **Performance:** Slower but compatible with Safari
- **Features:** Identical to morph-lab.html

#### **README.md**
- **Purpose:** Project overview, quick start, feature list
- **Target Audience:** New users, GitHub visitors
- **Sections:**
  - Features overview
  - Getting started
  - Technical details
  - License info
  - Troubleshooting (quick reference)
- **Length:** ~500 lines

#### **LICENSE**
- **Type:** MIT License
- **Purpose:** Legal licensing for the Morph Lab project itself
- **Coverage:** Code, HTML, CSS, JavaScript
- **Not covered:** Dependencies (see ATTRIBUTION.md)

#### **ATTRIBUTION.md**
- **Purpose:** Third-party library licenses and attribution
- **Includes:**
  - D3.js (ISC License)
  - Face API (MIT License)
  - TensorFlow.js (Apache 2.0)
  - JSZip (MIT/GPLv3 dual license)
  - Browser APIs (W3C Standard)
- **Compliance:** All licenses fully respected
- **No conflicts:** Compatible license stack

#### **CONTRIBUTING.md**
- **Purpose:** Guide for potential contributors
- **Content:**
  - Bug reporting instructions
  - Feature request process
  - Code submission workflow
  - Development setup
  - Code style guidelines
  - Testing checklist
  - Git commit conventions
- **Target Audience:** Open source contributors

#### **.gitignore**
- **Purpose:** Tell Git which files to ignore
- **Includes:**
  - OS files (.DS_Store, Thumbs.db)
  - IDE configs (.vscode, .idea)
  - Build artifacts (node_modules, dist)
  - Environment files (.env)
  - Logs and temp files
  - Typical video exports (*.mp4, *.webm)

#### **REPOSITORY_CONTENTS.md**
- **Purpose:** This file — describes what's in the repo
- **Use:** Help contributors understand file organization

---

### docs/ Folder

#### **docs/MANUAL.md**
- **Purpose:** Comprehensive user guide
- **Length:** ~1000 lines
- **Content:**
  - Getting started walkthrough
  - Single-pair mode step-by-step
  - Batch mode instructions
  - Settings customization
  - Advanced techniques
  - Troubleshooting (detailed)
  - Glossary of terms
  - Keyboard shortcuts
- **Target Audience:** End users, detailed reference
- **Format:** Markdown with tables and code examples

#### **docs/SCREENSHOTS.md**
- **Purpose:** Describe each screenshot
- **Content:**
  - What each screenshot shows
  - How to interpret the UI
  - Specifications (dimensions, size, theme)
  - Usage recommendations
- **Links to:** screenshots/ folder images

---

### screenshots/ Folder

All screenshots are **1200×800 px** PNG files captured in a headless browser on a server (not the user's computer).

#### **screenshots/01-landing-page.png** (352 KB)
- The index.html landing page
- Shows app introduction, feature list, launch buttons
- Gradient background, light theme
- First impression for new users

#### **screenshots/02-main-app-light.png** (30 KB)
- Main Morph Lab interface
- Light mode (default)
- Shows header, image panels, controls
- Clean, bright appearance

#### **screenshots/03-main-app-dark.png** (30 KB)
- Same interface, dark mode
- Demonstrates theme toggle
- High contrast on dark background
- Eye-friendly for low-light use

#### **screenshots/04-settings-format.png** (49 KB)
- Settings popout with Format tab active
- Shows aspect ratio selection
- Demonstrates popout UI positioning

#### **screenshots/05-settings-export.png** (60 KB)
- Settings popout with Export tab active
- Shows sliders (hold time, transition, FPS)
- Format selector (MP4 / WebM)
- Export button visible

#### **screenshots/06-batch-mode.png** (45 KB)
- Interface switched to Batch Sequence mode
- Shows drop zone, file pickers
- Thumbnail strip, transition controls
- Demonstrates multi-image workflow

---

## Total Repository Size

| Category | Size |
|----------|------|
| HTML Files | ~248 KB (3 files) |
| Documentation | ~60 KB (4 Markdown files) |
| Screenshots | ~576 KB (6 PNG files) |
| License/Config | ~5 KB (3 files) |
| **Total** | **~889 KB** |

---

## What's NOT Included

### External Libraries
All libraries are loaded **from CDN**, not bundled:
- D3.js (Delaunay triangulation)
- TensorFlow.js (ML models)
- Face API (face detection)
- JSZip (ZIP file creation)

**Why:** Keeps repository small, ensures latest versions

### Build Artifacts
- No `node_modules/` directory
- No bundled assets
- No compiled files
- **Why:** Single-file HTML apps don't need a build step

### User-Generated Content
- No sample images
- No export videos
- No cache files
- **Why:** Keep repo clean; users can test with their own files

---

## How to Use These Files

### For GitHub
1. Clone the repository
2. Enable GitHub Pages in settings
3. Set source to main branch, root folder
4. Your live demo: `https://yourusername.github.io/morph-lab`

### For Local Development
1. Clone the repo
2. Open `index.html` in a browser
3. No build step, no dependencies to install
4. Edit HTML/CSS/JS directly

### For Contribution
1. Fork the repo
2. Create a feature branch
3. Make changes following CONTRIBUTING.md
4. Submit a pull request

---

## File Permissions

All files are appropriate for public GitHub hosting:
- ✅ HTML/CSS/JS: Open source
- ✅ Documentation: MIT-compatible
- ✅ Screenshots: Original artwork, free to use
- ✅ Licenses: Properly attributed

---

## Future Additions

Potential files to add later:

- `CHANGELOG.md` — Release notes and version history
- `CONTRIBUTORS.md` — List of contributors
- `SECURITY.md` — Security policy and reporting
- `package.json` — If transitioning to Node.js build
- `.github/workflows/` — CI/CD pipelines (if added)
- `tests/` — Automated test files (if testing framework added)

---

**Created:** October 24, 2026  
**Total Files:** 13 (excluding this inventory)  
**Status:** Ready for GitHub upload
