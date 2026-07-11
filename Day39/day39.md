<div align="center">

# 📄 PDF Splitter & Merger

**A premium, single-file PDF utility that runs entirely in your browser — no uploads, no servers, no backend.**

</div>

---

## Overview

**PDF Splitter & Merger** is a self-contained, single-page web app for splitting and merging PDF documents — built to feel like a polished commercial tool rather than a weekend script. Every operation (rendering thumbnails, extracting pages, stitching documents together) happens **locally in the browser**. Files are never uploaded anywhere, which makes the tool fast, private, and safe to use on sensitive documents.

The entire application — markup, styles, and logic — lives in a **single HTML file**, making it trivial to deploy (GitHub Pages, any static host, or just double-click it locally).

## Why this exists

Most free online PDF tools require uploading your document to a third-party server — a non-starter for anything sensitive (contracts, transcripts, medical records, financial statements). This project proves that a genuinely polished, feature-complete PDF workflow tool can be built with **zero backend**, using only in-browser libraries, while still matching the UX quality of paid SaaS tools.

## Features

### ✂️ PDF Splitter
- Drag-and-drop or click-to-browse PDF upload with automatic page-count detection
- Visual page thumbnails for every page, lazily rendered with `IntersectionObserver` for performance on large documents
- Four split methods in one tool:
  - **Custom ranges** — define multiple independent page ranges, each exported as its own file
  - **Split after pages** — click a "cut point" between thumbnails, or type page numbers, to break the document at exact points
  - **Every N pages** — automatically chunk the document into equal-sized files
  - **Extract selected** — click any pages to pull them into a new file (combined, or one file per page)
- Live **output preview** that lists every file that will be generated, with page counts, before you click Split
- Real-time validation — invalid or out-of-range inputs are highlighted immediately with a clear inline error
- Multiple resulting files can be downloaded individually or bundled into a single `.zip`

### 🧷 PDF Merger
- Multi-file drag-and-drop or file picker upload
- Each file shown with a first-page thumbnail preview and page count
- Native drag-and-drop reordering of files before merging
- Live summary bar — total files, total pages, and estimated output size
- One-click merge into a single downloadable PDF

### 🎨 Experience
- Full dark / light theme toggle (respects system preference on first load)
- Keyboard shortcuts (`1` / `2` to switch tools, `Ctrl/⌘+O` to open files, `T` to toggle theme, `?` for a shortcuts reference)
- Toast notifications and a processing overlay for long-running operations
- Fully responsive layout, down to mobile
- Accessible by design: visible focus states, ARIA labels/roles on all interactive controls, `aria-live` status regions, and respect for `prefers-reduced-motion`

## Tech Stack

| Layer | Choice | Why |
|---|---|---|
| Structure / Styling | Vanilla HTML5 + CSS (custom properties) | Zero build step, one portable file |
| Logic | Vanilla JavaScript (ES6+) | No framework overhead for a tool this size |
| PDF manipulation | [pdf-lib](https://pdf-lib.js.org/) | Create, split, and merge PDFs entirely client-side |
| PDF rendering | [pdf.js](https://mozilla.github.io/pdf.js/) | Renders page thumbnails to `<canvas>` |
| Archiving | [JSZip](https://stuk.github.io/jszip/) | Bundles multi-file split output into a single `.zip` download |
| Fonts | Fraunces (display), Inter (body), IBM Plex Mono (data) | Loaded from Google Fonts |

No React, no bundler, no `npm install` — open the file and it works.

## Architecture & Design Decisions

**Single file by design.** Everything — markup, CSS, and JS — lives in one `.html` file inside an IIFE. This was a deliberate constraint: it makes the tool trivially shareable (email it, drop it on any static host, or open it directly from disk) with no build pipeline to maintain.

**Two independent processing pipelines per PDF.** Each uploaded file is loaded twice, into two different libraries, on purpose:
- **pdf.js** parses the file for **visual rendering** — thumbnails are painted to `<canvas>` elements.
- **pdf-lib** parses the same bytes for **structural manipulation** — copying, extracting, and recombining pages.

This separation exists because pdf.js is optimized for rendering and has no page-editing API, while pdf-lib is optimized for document manipulation and has no rendering path. Keeping them decoupled means each library is only ever asked to do what it's good at.

**Lazy thumbnail rendering.** For large PDFs, rendering every page thumbnail up front would block the main thread and hurt perceived performance. Thumbnails are rendered on-demand via `IntersectionObserver` as they scroll into view, with a graceful fallback to eager rendering in browsers that lack the API.

**A single source of truth for split output.** Regardless of which split method is active (ranges, cut points, every-N, or extract), all four modes resolve down to one shared `computeOutputPlan()` function that returns a list of `{ label, pages, error }` objects. The output preview list, the validation highlighting, and the actual PDF-generation step all read from this same plan — so what you see in the preview is guaranteed to be exactly what gets produced.

**Reordering via the DOM, not a separate index array.** The merge file list uses native HTML5 drag-and-drop directly on the rendered rows; after a drop, the in-memory file order is re-synced by reading the DOM's current row order. This keeps the visual order and the data order from ever drifting apart.

**No `innerHTML` for dynamic, user-influenced content.** DOM nodes for thumbnails, range rows, and file list items are built with a small `el()` helper using `createElement` / `textContent`, avoiding injection risk from PDF filenames or content and sidestepping reflow/parsing overhead from repeated HTML string parsing.

## Getting Started

No installation required.

```bash
git clone https://github.com/<your-username>/pdf-splitter-merger.git
cd pdf-splitter-merger
open pdf-splitter-merger.html   # or just double-click the file
```

### Deploying to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set the source branch to `main` (or `gh-pages`) and root directory
4. Your live demo will be available at `https://<your-username>.github.io/pdf-splitter-merger/`

> **Note on offline use:** the three libraries (pdf-lib, pdf.js, JSZip) load from a CDN on first visit. After that, most browsers will serve them from cache, so the app continues to work without a connection — but it needs that first online load to fetch them.

## Browser Support

Tested on the latest versions of Chrome, Edge, Firefox, and Safari. Requires support for `<canvas>`, the File API, and ES6+ JavaScript. `IntersectionObserver` is used when available with an automatic fallback.

## Privacy

No file, filename, or byte of content is ever sent over the network. All parsing, rendering, splitting, and merging happens using in-memory `ArrayBuffer`s in the browser tab. Closing the tab discards everything.

## Roadmap

- [ ] Page rotation and deletion within the splitter
- [ ] Drag-to-reorder pages within a single PDF before splitting
- [ ] PDF compression on export
- [ ] Password protection / encryption on output files
- [ ] Per-file page range selection when merging (merge a subset of each source PDF)

---

<div align="center">
Built as a demonstration of a fully client-side, privacy-first PDF workflow tool.
</div>
