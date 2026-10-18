# Image Resizer — kayralrics.com

A precision image-resizing website with a distinctive pure-black and signal-red interface. The entire user-facing interface is in English and credits **kayralrics.com**.

## Run locally

1. Extract `image-resizer.zip`.
2. Open `index.html` in a modern desktop or mobile browser.
3. Standard browser-supported formats work without a build step. An internet connection is required only when the site needs to load an extended decoder for a format your browser cannot open natively.

For hosting, upload `index.html` to any static web host. No application server or API key is required.

## Features

- Precision width/height controls, aspect-ratio locking, and popular pixel presets
- Three fit modes: Contain, Cover, and Stretch
- Multi-image queue, drag-and-drop, live preview, individual downloads, and ZIP download
- Output formats: PNG, JPEG, WebP, AVIF (when supported), GIF, BMP, TIFF, SVG, PSD, ICO, JP2, JXL, TGA, PPM, PGM, PBM, QOI, and XCF (depending on the available codec)
- Lossy quality control, transparency controls, and selectable background fill
- Local processing: selected image files are not uploaded to a server
- Extended-format decoding on demand: HEIC/HEIF and TIFF-specific decoders, plus a browser-side WebAssembly ImageMagick engine for additional formats such as BMP, GIF, TIFF, and PSD
- Responsive layout, keyboard-accessible controls, and red/black styling

## Format support notes

Image formats are not one universal interchangeable standard. The browser's built-in image codecs are used first; optional decoders are loaded when required. In particular:

- HEIC/HEIF and TIFF may require their optional decoders.
- The extended WebAssembly engine runs in the browser and may need an internet connection to load its code the first time.
- GIF input is treated as a still image; animated frames are not preserved by the resizing workflow.
- SVG export wraps the resized raster result in an SVG container; it does not recreate vector shapes from a raster source.
- AVIF output depends on encoder support in the current browser or extended codec.
- Camera RAW and proprietary formats vary by camera model and embedded preview. No browser-only tool can guarantee every proprietary or obscure format.
- Very large images may be rejected to protect browser memory. Output is capped at 16,000 pixels per side and 100 million pixels total.

The browser-side decoder processes image bytes locally; optional decoder scripts and WebAssembly are downloaded from their public CDN/source when needed. The image itself is not sent to that service.

## Project files

- `index.html` — complete website
- `README.md` — this guide

## Credit

**kayralrics.com**
