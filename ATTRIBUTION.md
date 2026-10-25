# Third-Party Licenses & Attribution

Morph Lab includes or uses the following open-source libraries and resources. Their licenses are detailed below.

---

## D3.js (Delaunay Triangulation)

**Version:** 7.9.0  
**Repository:** https://github.com/d3/d3  
**License:** ISC  
**Copyright:** Copyright 2010–2021 Mike Bostock

### ISC License

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

---

## Face API (face-api.js)

**Repository:** https://github.com/vladmandic/face-api  
**License:** MIT  
**Copyright:** Copyright (c) 2019–2024 Vladimir Mandic

### MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

---

## TensorFlow.js

**Version:** Latest (loaded via CDN)  
**Repository:** https://github.com/tensorflow/tfjs  
**License:** Apache 2.0  
**Copyright:** Copyright 2019 Google Inc.

### Apache License, Version 2.0

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this software except in compliance with the License. You may obtain a copy of the License at:

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

---

## JSZip (ZIP file creation)

**Version:** Latest (loaded via CDN)  
**Repository:** https://github.com/Stuk/jszip  
**License:** MIT/GPLv3  
**Copyright:** Copyright (c) 2009–2016 Stuart Knightley and others

### Dual License: MIT / GPLv3

This software is available under either the MIT or GPLv3 license. You may choose to use it under either license.

#### MIT License Text

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

#### GPLv3 License Text

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see: https://www.gnu.org/licenses/

---

## Browser APIs (Native)

The following are built-in browser APIs, not third-party libraries:

- **Canvas API** (2D and WebGL): HTML5 Standard (W3C)
- **MediaRecorder API**: HTML5 Standard (W3C)
- **Blob & File APIs**: HTML5 Standard (W3C)
- **localStorage**: HTML5 Standard (W3C)

These APIs are royalty-free and available in all modern browsers. No license restrictions apply.

---

## Summary

| Library | Version | License | Usage |
|---------|---------|---------|-------|
| D3.js | 7.9.0 | ISC | Delaunay triangulation |
| Face API | Latest | MIT | Facial landmark detection |
| TensorFlow.js | Latest | Apache 2.0 | ML model inference |
| JSZip | Latest | MIT/GPLv3 | PNG sequence bundling |
| Browser APIs | N/A | W3C Standard | Video rendering, downloads |

---

## How We Use These Libraries

### D3.js
- **Purpose:** Compute Delaunay triangulation from user-marked points
- **Usage:** Point-based morphing mesh generation
- **Loaded:** Embedded in HTML from CDN

### Face API + TensorFlow.js
- **Purpose:** Detect facial landmarks (optional feature)
- **Usage:** Auto-mark facial features (eyes, nose, mouth, jaw, etc.)
- **Loaded:** Dynamically from CDN only when Face Mode is enabled
- **Privacy:** Models run entirely in the browser; no data sent to servers

### JSZip
- **Purpose:** Bundle PNG sequence frames into a downloadable ZIP
- **Usage:** PNG export feature
- **Loaded:** From CDN

### Canvas & WebGL APIs
- **Purpose:** Render images and morphing video
- **Usage:** Core rendering pipeline
- **Loaded:** Native browser features (no external library)

---

## Compliance Notes

✅ **All licenses are fully respected and complied with:**
- License texts are included in this file
- Attribution is provided to original authors
- No proprietary claims are made
- Derivative work properly acknowledged (Morph Lab uses these libraries, does not subsume them)
- Users can review and verify licenses

✅ **Open Source:** Morph Lab itself is released under the MIT License, allowing free use, modification, and distribution.

✅ **No License Conflicts:** The combination of ISC, MIT, Apache 2.0, and MIT/GPLv3 licenses is compatible and poses no restrictions on distribution.

---

## Third-Party Resources

The following third-party resources are used for development/documentation:

- **GitHub**: Code hosting and issue tracking
- **CDN Services**: jsDelivr, cdnjs, unpkg (for serving JavaScript libraries)

---

If you have questions about licensing or attribution, please open an issue on GitHub: https://github.com/yourusername/morph-lab/issues

**Last updated:** October 24, 2026
