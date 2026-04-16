# InnoGen QR Studio

A lightweight, browser-based tool for generating branded QR code PNG assets for InnoGen (and Solvang) use cases. It supports QR codes for website links, plain text, and a “Digital Business Card (vCard)” format that works well on both Android and iPhone.

## Why this exists

- Speeds up creation of consistent, branded QR codes for posters, packaging, brochures, booths, email signatures, and internal materials.
- Reduces back-and-forth between teams by letting anyone generate a ready-to-use PNG asset in seconds.
- Ensures brand consistency through built-in icon presets and color control.

## Key Features

- **QR Content Types**
  - **URL | Label | Code Scanning**: Paste a URL, plain text, labels, or multi-line content.
  - **Digital Business Card (vCard)**: Generate a scannable contact card that can be saved into phone contacts.

- **Branding Controls**
  - **QR color picker** (brand-aligned color output)
  - **Center logo scale** slider
  - **Center logo selection**
    - Use uploaded image (default)
    - InnoGen icon (`favicon.png`)
    - Solvang icon (`solvang-favicon.png`)
    - No icon

- **Output**
  - Generates a high-resolution **PNG** QR asset for download.

## Getting Started

### Option A: Open directly (simplest)
1. Open `index.html` in a browser (Chrome/Edge recommended).
2. Choose a content type (URL/Text or vCard).
3. Adjust color/logo options.
4. Click **Generate QR Asset**.
5. Click **Download PNG Asset**.

### Option B: Run as a local static site (recommended for some browsers)
From the project folder, run one of the following:

**PowerShell (Windows)**
```powershell
python -m http.server 8000
```

Then open:
- http://localhost:8000/

## Usage Guide

### 1) URL | Label | Code Scanning
- Paste or type any content into the multi-line textbox.
- Use this for links, labels, short instructions, or internal codes.

### 2) Digital Business Card (vCard)
Fill in:
- **Full Name (FN)** (required)
- Organization, mobile (TEL), email, address, website (optional)

The generated vCard includes both:
- `N:` (structured name, helps iPhone prioritize the person’s name)
- `FN:` (display name)

This improves compatibility so iPhone and Android both show the person’s name clearly rather than emphasizing the organization.

## Files

- `index.html` — Application UI and logic
- `favicon.png` — InnoGen icon option
- `solvang-favicon.png` — Solvang icon option

## Notes / Limitations

- This is a static, client-side tool: it runs entirely in the browser.
- QR generation uses a CDN-hosted library (`qrcodejs`), so an internet connection may be required unless you replace it with a local copy.
- Some phone camera apps interpret vCards slightly differently; the tool is designed to be broadly compatible.

## Troubleshooting

- **Center logo not appearing**
  - Ensure a center logo option is selected.
  - If using uploaded image, confirm you selected a file.
- **vCard saves but name looks wrong on iPhone**
  - Use a clear full name (e.g., “Juan Dela Cruz”).
  - If your standard format is “Last, First Middle”, enter it that way for better parsing.

## License / Ownership

Internal use (InnoGen Pharmaceuticals Inc.). Update this section if you plan to open-source the project.
