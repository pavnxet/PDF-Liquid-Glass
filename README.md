# PDF Liquid Glass

A fully client-side PDF toolkit with a liquid glass UI. **Everything runs in your browser** — no files are ever uploaded to any server.

Live Demo: [https://pavnxet.github.io/PDF-Liquid-Glass/](https://pavnxet.github.io/PDF-Liquid-Glass/)

---

## Features

### Compress PDF
- **Target Size Mode** — set an exact file size target (KB or MB). The tool iteratively reduces JPEG quality and canvas resolution until the output fits.
- **Quality Mode** — pick a fixed JPEG quality (10–95%). Single pass, no size constraint. You get exactly the quality you chose.
- Before/after size comparison shown after compression.

### Merge PDF
- Combine multiple PDFs into one.
- **Drag-and-drop reordering** — rearrange files before merging.
- **Page range selector** — pick specific pages from each PDF (e.g. `1-3,5,7-9`). Leave empty to include all pages.
- Uses `pdf-lib.copyPages()` for lossless merging (no rasterization).

### Images to PDF
- Combine JPG/PNG images into a single PDF.
- Drag-and-drop reordering.
- Embeds images at original resolution.

### Watermark
- Stamp text diagonally across every page of a PDF.
- Configurable text, opacity, and font size.
- Live preview updates as you adjust settings.

### Clear Links
- Remove link annotations from PDFs.
- Optionally remove all annotations.
- Scrub metadata (title, author, subject, keywords, producer, creator).
- Remove bookmarks/outlines.
- Batch process multiple files.

---

## Tech Stack

| Dependency | Purpose |
|------------|---------|
| [pdf.js](https://mozilla.github.io/pdf.js/) v4.4.168 | Parse and render PDF pages to canvas |
| [pdf-lib](https://pdf-lib.js.org/) v1.17.1 | Create, modify, merge, and save PDFs |
| Google Fonts (Outfit, Sora, Lora, Playfair Display) | Typography |

All loaded from CDN. No npm, no bundler, no build step.

---

## Design

The UI uses a **Liquid Glass** design system:

- Animated aurora mesh background with floating color blobs
- Translucent glassmorphic surfaces with specular edge highlights
- Cursor-following spotlight effect
- Warm amber/cocoa/cream palette
- Responsive — works on mobile, tablet, and desktop

---

## Usage

### Option 1: Open locally
Download `index.html` and open it in any modern browser. No server needed.

### Option 2: GitHub Pages
1. Fork or clone this repo
2. Go to Settings > Pages
3. Set source to the `main` branch
4. Your site will be live at `https://<username>.github.io/<repo>/`

### Option 3: Host anywhere
Drop `index.html` on any static host (Netlify, Vercel, Cloudflare Pages, etc.).

---

## Privacy

- All processing happens **entirely in your browser** using Web APIs (Canvas, Blob, FileReader).
- No data is sent to any server.
- No cookies, no analytics, no tracking.
- After compression/merge, output files are created as Blob URLs that exist only in your browser's memory.

---

## Browser Support

Requires a modern browser with support for:
- `backdrop-filter` (CSS)
- ES Modules (`import`)
- `Canvas.toBlob()`
- `FileReader` / `ArrayBuffer`

Tested on Chrome, Edge, Firefox, and Safari 18+.

---

## Limitations

- **PDF to text/searchable**: Compressed PDFs are rasterized (pages become JPEG images). Text is no longer selectable or searchable. This is the trade-off for hitting exact file size targets.
- **Max file size**: 300 MB per PDF input.
- **Max files**: 5 files per batch (compress), unlimited (merge/clean).
- **Watermark font**: Uses pdf-lib's default Helvetica. Custom fonts require embedding.

---

## License

MIT — use it however you want.
