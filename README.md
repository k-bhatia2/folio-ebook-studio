# Folio — eBook Studio

A complete browser-based eBook formatting tool inspired by the core workflow of KDP Builder's eBook formatter, with original branding and interface design.

## Standalone app

Open the supplied `Folio.html` in Chrome, Edge, Firefox or Safari. All document libraries are bundled into that file. No local server is required for this standalone edition. Keep the source ZIP if you want to customize or host the app.

## Run the source locally

From this folder, run:

```sh
python -m http.server 4173 --bind 127.0.0.1
```

Open http://127.0.0.1:4173. No build step, API keys, database, or package installation is required. Serve this folder with any static web host to deploy independently. HTTPS is recommended for production.

## Features

- Import Word (.docx, up to 20 MB), plain text (.txt), or pasted text.
- Detect Word Heading 1 (or Heading 2 when no Heading 1 exists), chapter/part markers, and Markdown headings in text files.
- Add, rename, edit, reorder, remove, and undo removal of chapters.
- Preserve basic emphasis, lists, tables, embedded PNG/JPEG/GIF images, and Unicode text.
- Set title, subtitle, author, language, publisher, copyright year, and description.
- Include dedication, author biography, closing message, and custom copyright notice.
- Add an optional PNG/JPEG cover, choose three reading styles, change text size and paragraph style.
- Navigate a live tablet/phone layout preview.
- Run basic structural preflight checks, with required title, author, and chapter content.
- Download a complete EPUB 3, a one-chapter EPUB, or a cleaned DOCX.
- Download a ZIP containing EPUB, DOCX, metadata JSON, publishing checklist, and editable project backup.
- Save a draft locally and restore portable JSON project backups.

## GitHub Pages

In repository **Settings → Pages**, choose **Deploy from a branch**, then **main** and **/ (root)**. No build workflow or secrets are needed.

## Files

- `index.html`: semantic application interface.
- `styles.css`: responsive styling.
- `app.js`: import, editing, local saving, validation, and export logic.
- `*.min.js` and `docx.iife.js`: pinned, bundled third-party libraries.
- `*-LICENSE.txt`: third-party license notices.
- `.nojekyll`: serves the static files directly on GitHub Pages.

## Privacy and limits

Manuscripts are processed entirely in the browser. No manuscript uploads, analytics, payment processing, or external AI calls are made. Google Fonts supplies interface fonts; browser fallback fonts work when offline. Browser storage can fill up or be cleared, so save a project backup for important work. Only one local working draft is retained per browser origin.

This is a reflowable, text-focused formatter. Word print pagination, running headers/footers, floating shapes, exact table layout, and elaborate print styling are simplified. Review complex tables, images, links, and notes in exported files. Word contents are a readable list; the EPUB contents are navigable. Reader fonts and pagination may override the preview. Metadata JSON is a reference file, not an automatic KDP upload format.

The browser preflight is a structural check, not a full EPUBCheck service or a guarantee of acceptance by any publishing platform. There is no direct publishing-to-Amazon integration. This app is designed for static hosting on GitHub Pages. Manuscripts and local drafts are never committed to this repository.

## Verification performed

- Browser-tested sample workflow, metadata edits, DOCX and TXT import, cover upload, styles, responsive layout, local draft restoration, and project restoration.
- Tested chapter add/edit/reorder/remove/undo and blocking export when required metadata is missing.
- Downloaded the actual full publishing package and one-chapter EPUB from the browser.
- Parsed generated EPUB and DOCX XML; confirmed Word emphasis, tables, images, and Hindi text.
- Validated a full sample EPUB and an imported rich-document EPUB with official EPUBCheck 5.4.0: zero errors and warnings for both fixtures.
- Confirmed one-chapter export contains exactly one manuscript chapter.

## Third-party libraries

- JSZip 3.10.1 — MIT / GPLv3, used under MIT.
- Mammoth 1.11.0 — BSD-2-Clause.
- docx 9.5.1 — MIT.

License texts are included alongside the bundled libraries.
