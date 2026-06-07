# ScrubFew

**Strip hidden metadata from your files — runs entirely in your browser, open source, for everyone.**

ScrubFew is part of the **Few** toolkit, alongside the rest of the suite (see the full list below).
It removes the metadata baked into your files — EXIF/GPS in photos, author and edit history in Office documents, producer info in PDFs — **locally**, so what you can't see doesn't travel with the file when you share it.

It pairs naturally with MaskFew: **MaskFew cleans the visible content, ScrubFew cleans the hidden metadata.** Together they make a file safe to share.

It's a single, self-contained web page. No backend, no build step, no upload, no tracking.

🔗 **Live:** https://silvestroparisi.github.io/ScrubFew/

> Clean the content with MaskFew. Strip what you can't see with ScrubFew.

## What it strips

- **Images** (PNG, JPG, WebP, GIF, BMP) — the image is re-encoded on a canvas, which drops **all** embedded metadata: EXIF, GPS coordinates, camera make/model and serial, timestamps, thumbnails and comments. Output is a fresh PNG / JPEG / WebP. It detects and reports EXIF, GPS, XMP, IPTC and ICC before cleaning.
- **PDF** — clears the document information: title, author, subject, creator, producer and creation/modification dates.
- **Office** (DOCX, XLSX, PPTX) — blanks the document properties: author, last-modified-by, company, manager, template, dates and revision number. Comments and tracked changes are **flagged** so you can remove them in the source app.

## Best-effort, not magic

ScrubFew removes embedded metadata reliably, but it makes no guarantee of total sanitization:

- A PDF's **XMP** metadata stream and deeply embedded objects may not be cleared.
- Office **comments and tracked changes** are detected and flagged, not auto-removed — handle them in Word/Excel/PowerPoint.
- Animated **GIFs** are flattened to a single frame on re-encode.

Always review a file before sharing it where it matters.

## How to use it

1. Open the page (or download `index.html` and open it locally — it works offline).
2. Drop in a file, or click to choose one.
3. Review the report of what's hidden inside it.
4. Click **Scrub & download** to get the cleaned copy.

Everything happens on your machine. The file is never uploaded.

## Privacy

There's no backend. The whole tool is a single static page: no account, no upload, no server waiting to receive your file. Open your browser's **DevTools → Network** and check — the only requests are the page itself and, for PDF/Office, the open-source libraries it uses ([JSZip](https://stuk.github.io/jszip/) and [pdf-lib](https://pdf-lib.js.org/)). Your file never leaves the browser.

## The Few toolkit

- [**FirstFew**](https://silvestroparisi.github.io/FirstFew/) — prioritize the few that matter
- [**FixFew**](https://silvestroparisi.github.io/FixFew/) — verify and remediate vulnerabilities
- [**MaskFew**](https://silvestroparisi.github.io/MaskFew/) — anonymize a file before you share it
- [**AskFew**](https://silvestroparisi.github.io/AskFew/) — a private AI that runs in your browser
- **ScrubFew** — strip hidden metadata before you share
- [**RopaFew**](https://silvestroparisi.github.io/RopaFew/) — build your GDPR Article 30 register
- [**GapFew**](https://silvestroparisi.github.io/GapFew/) — a multi-framework compliance gap self-assessment
- [**CloseFew**](https://silvestroparisi.github.io/CloseFew/) — turn your gaps into a remediation plan

## License

[MIT](LICENSE) © 2026 Silvestro Parisi
