# Contributing to Morph Lab

Thank you for your interest in contributing to Morph Lab! This guide will help you get started.

## Code of Conduct

Be respectful, inclusive, and constructive. We're building something cool together.

## How to Contribute

### Reporting Bugs

1. **Check existing issues** to avoid duplicates
2. **Create a new issue** with:
   - Clear title and description
   - Steps to reproduce
   - Browser/OS info (Chrome 120 on Windows 11, etc.)
   - Screenshots if possible
   - Console errors (F12 → Console tab)

### Suggesting Features

1. Open an issue titled `[Feature Request] Your idea here`
2. Describe the use case and why it would be useful
3. Include mockups or examples if possible

### Submitting Code

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/morph-lab.git
   cd morph-lab
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Edit HTML/CSS/JS directly (no build step required)
   - Test in multiple browsers
   - Keep formatting consistent

4. **Commit and push**
   ```bash
   git add .
   git commit -m "Add feature: description of change"
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**
   - Link related issues
   - Describe what changed and why
   - Include screenshots if UI-related

## Development Workflow

### Testing Locally

```bash
# Option 1: Direct file access
open index.html

# Option 2: Local web server (Python 3)
python -m http.server 8000
# Then visit http://localhost:8000
```

### Browser Testing

Test in:
- Chrome (primary)
- Firefox
- Safari (especially the Canvas2D fallback)
- Edge

### Debugging

1. **Open DevTools:** F12 (or Cmd+Option+I on Mac)
2. **Console tab:** Check for errors
3. **Network tab:** Monitor requests (should be none except CDN libraries)
4. **Sources tab:** Set breakpoints in code

### File Structure

```
morph-lab/
├── index.html                 # Landing page
├── morph-lab.html            # Main app (WebGL)
├── morph-lab-safari.html     # Fallback (Canvas2D)
├── README.md                 # Project overview
├── MANUAL.md                 # User guide
├── CONTRIBUTING.md           # This file
├── LICENSE                   # MIT License
├── ATTRIBUTION.md            # Third-party licenses
├── .gitignore
└── screenshots/              # UI screenshots
    ├── 01-landing-page.png
    ├── 02-main-app-light.png
    └── ...
```

## Code Style

### HTML

- Use semantic HTML5 elements
- Indent with 2 spaces
- Self-closing tags: `<input type="range" />`

### CSS

- Use CSS custom properties for colors/spacing
- Prefix vendor-specific properties (-webkit-, -moz-, etc.)
- Media queries at the bottom of rule sets

### JavaScript

- Use ES2020+ features (const, arrow functions, destructuring, etc.)
- Camel case for variables: `myVariable`
- Upper case for constants: `CONSTANT_VALUE`
- Comment complex logic

### Example

```javascript
// Compute triangulation for morphing mesh
const CROP_MIN_SCALE = 0.2;  // constant
const CROP_MAX_SCALE = 3;

function computeTriangulation(points) {
  // Use D3 Delaunay for point-based morphing
  const triangles = d3.Delaunay.from(points);
  return triangles;
}
```

## Making Changes

### Add a Feature

1. Identify where code lives (look for relevant `id`, `class`, or function name)
2. Make focused, minimal changes
3. Test in multiple browsers
4. Document with comments if non-obvious

### Fix a Bug

1. Write a comment describing the fix
2. Include the issue number: `// Fixes #123`
3. Test the fix in relevant browsers

### Update Documentation

1. Edit `.md` files in this repository
2. Run spell check if available
3. Test Markdown rendering (GitHub shows previews)

## Git Commit Messages

Follow this format:

```
Add feature: brief description of what changed

Longer explanation if needed. Reference issues with #123.
Explain why this change was necessary.
```

Examples:

- `Add feature: keyboard shortcuts for point marking (u=undo, c=clear)`
- `Fix bug: face detection points offset on cropped images (Fixes #42)`
- `Update docs: add troubleshooting section to MANUAL.md`
- `Refactor: simplify point dragging logic in crop modal`

## Testing Your Changes

### Before Submitting

- [ ] App loads without console errors
- [ ] Feature works as intended
- [ ] No console warnings or errors
- [ ] Tested in Chrome, Firefox, Safari
- [ ] Existing features still work
- [ ] Settings/theme persistence works
- [ ] Light & dark mode both look good
- [ ] Responsive on mobile (if applicable)

### Performance

- [ ] Renders don't stall the UI
- [ ] Large images (4K) don't crash
- [ ] Memory usage is reasonable
- [ ] No memory leaks on repeated use

## Pull Request Checklist

Before opening a PR:

- [ ] Feature branch created from latest main
- [ ] Code follows style guide
- [ ] No console errors/warnings
- [ ] Tested in multiple browsers
- [ ] Documentation updated (if needed)
- [ ] Changes are focused and minimal
- [ ] Commit messages are clear

## Getting Help

- **Questions?** Open a discussion in GitHub Discussions (or an issue)
- **Stuck?** Comment on the related issue
- **Need guidance?** Look at existing issues/PRs for similar problems

## Recognition

Contributors will be recognized in:
- GitHub Contributors page
- CONTRIBUTORS.md file (coming soon)
- Release notes for major changes

Thank you for contributing! 🙏

---

**Last updated:** October 24, 2026
