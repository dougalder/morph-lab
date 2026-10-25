# GitHub Setup Guide for Morph Lab

This guide walks you through uploading Morph Lab to GitHub and enabling GitHub Pages.

## Prerequisites

- GitHub account (create at https://github.com if needed)
- Git installed on your computer (`git --version` to check)
- The `morph-lab-repo.zip` file extracted to a folder

## Step 1: Create a New Repository on GitHub

1. Go to https://github.com/new
2. **Repository name:** `morph-lab` (or your preferred name)
3. **Description:** "A browser-based image morphing tool" (optional)
4. **Public** (recommended for open-source projects)
5. **Add a README:** Leave unchecked (we have our own README.md)
6. Click **Create repository**

## Step 2: Extract the ZIP File

1. Download `morph-lab-repo.zip` from this conversation
2. Extract it:
   - **Windows:** Right-click → Extract All
   - **macOS:** Double-click (auto-extracts)
   - **Linux:** `unzip morph-lab-repo.zip`
3. You'll have a folder called `morph-lab-repo/` with all the contents

## Step 3: Set Up Git Locally

Open your terminal/command prompt in the extracted folder:

```bash
# Navigate to the extracted folder
cd morph-lab-repo

# Initialize git (if not already a repo)
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Morph Lab image morphing tool"

# Add your GitHub repository as the remote
git remote add origin https://github.com/YOUR-USERNAME/morph-lab.git

# Rename branch to main (if necessary)
git branch -M main

# Push to GitHub
git push -u origin main
```

**Replace `YOUR-USERNAME` with your actual GitHub username.**

## Step 4: Enable GitHub Pages

This makes your app live at `https://YOUR-USERNAME.github.io/morph-lab/`

### Method 1: Via GitHub Web UI (Easiest)

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. Scroll down to **"Pages"** in the left sidebar
4. **Source:** Select "Deploy from a branch"
5. **Branch:** Select `main` and `/root` folder
6. Click **Save**
7. Wait 1-2 minutes
8. You'll see a green box with your live URL: `https://YOUR-USERNAME.github.io/morph-lab/`

### Method 2: Via git (Command Line)

```bash
# No additional steps needed—GitHub Pages auto-detects index.html
```

## Step 5: Update README.md Links (Optional)

Open `README.md` in your editor and replace:

- `yourusername` with your GitHub username
- `https://yourusername.github.io/morph-lab` with your actual live URL

Example changes:

```markdown
# Before:
[Visit Live Demo](https://yourusername.github.io/morph-lab)
[Open an issue](https://github.com/yourusername/morph-lab/issues)

# After:
[Visit Live Demo](https://github.com/YOUR-USERNAME/morph-lab)
[Open an issue](https://github.com/YOUR-USERNAME/morph-lab/issues)
```

Then commit and push:

```bash
git add README.md
git commit -m "Update links to point to actual GitHub repository"
git push
```

## Step 6: Verify Everything Works

1. **Landing page:** https://YOUR-USERNAME.github.io/morph-lab/
2. **Main app:** https://YOUR-USERNAME.github.io/morph-lab/morph-lab.html
3. **Safari fallback:** https://YOUR-USERNAME.github.io/morph-lab/morph-lab-safari.html

All three should load without errors.

## File Checklist

Your GitHub repository should now contain:

```
✅ index.html                    (landing page)
✅ morph-lab.html               (main app)
✅ morph-lab-safari.html        (Safari fallback)
✅ README.md                    (project overview)
✅ LICENSE                      (MIT License)
✅ ATTRIBUTION.md               (third-party licenses)
✅ CONTRIBUTING.md              (contribution guide)
✅ REPOSITORY_CONTENTS.md       (file inventory)
✅ docs/MANUAL.md               (user guide)
✅ docs/SCREENSHOTS.md          (screenshot descriptions)
✅ screenshots/*.png             (6 UI screenshots)
✅ .gitignore                   (ignore rules)
```

## Customization Tips

### Custom Domain

If you own a domain, you can use it instead of GitHub Pages:

1. Go to **Settings → Pages**
2. Under "Custom domain," enter your domain: `morph-lab.example.com`
3. Follow the CNAME setup instructions

### Add More Sections to README

Common README sections:

```markdown
## Features
[...]

## Getting Started
[...]

## Usage
[...]

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md)

## License
MIT License—see [LICENSE](LICENSE) file
```

### Enable Discussions

1. Go to **Settings → Features**
2. Check **Discussions**
3. Users can ask questions without opening issues

### Add Topics

1. Go to **Settings** (gear icon, not left sidebar)
2. Scroll to **Topics**
3. Add tags: `image-morphing`, `web-app`, `animation`, `javascript`, etc.
4. This helps people discover your project

## Common Issues & Fixes

### "Cannot push to repository" error

**Problem:** Authentication failed  
**Solution:**
```bash
# Use GitHub CLI for easier auth
gh auth login

# Or generate a personal access token:
# https://github.com/settings/tokens
# Then use it as your password when pushing
```

### Pages not showing live

**Problem:** Green checkmark doesn't appear after 5 minutes  
**Solution:**
1. Check **Settings → Pages** again
2. Make sure index.html exists in root
3. Try rebuilding: Settings → Pages → Save again
4. Wait another 5 minutes

### App works locally but not on GitHub Pages

**Problem:** Network errors or missing files  
**Solution:**
- Check browser console (F12 → Console)
- Verify files exist in repository
- Check that CDN libraries load (D3.js, TensorFlow.js)
- Try clearing browser cache

## Next Steps

### Promote Your Project

1. **Share on social media:** Post a link with a screenshot
2. **Add to awesome lists:** Search GitHub for "awesome image morphing" lists
3. **Showcase on Portfolio:** Link from your website
4. **Open Issues:** Encourage feedback and contributions

### Keep It Updated

- Fix bugs when reported
- Add features from community requests
- Update documentation as you improve the app
- Respond to Pull Requests promptly

### Build the Community

- Welcome contributors
- Answer questions in Issues
- Create good first-issue labels
- Celebrate contributors in the CONTRIBUTORS.md file

## Getting Help

- **GitHub Docs:** https://docs.github.com/
- **GitHub Pages Guide:** https://pages.github.com/
- **Git Basics:** https://git-scm.com/book/en/v2/Getting-Started

---

## TL;DR (Quick Version)

```bash
# 1. Create repo on GitHub named "morph-lab"
# 2. Extract morph-lab-repo.zip
cd morph-lab-repo
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR-USERNAME/morph-lab.git
git branch -M main
git push -u origin main

# 3. Enable Pages in repo Settings
# 4. Wait 2 minutes
# 5. Visit https://YOUR-USERNAME.github.io/morph-lab/
# Done! 🎉
```

---

**Last updated:** October 24, 2026  
**Repository:** Ready to push to GitHub  
**Status:** All files verified ✅
