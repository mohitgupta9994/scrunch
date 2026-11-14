# Scrunch

Shrink photos, PDFs and videos right in your browser. Nothing gets uploaded.

Scrunch is a single web page that compresses files on your own device. Drop in a batch of images, PDFs and videos, pick how hard to squeeze, and save the smaller files. No account, no server, no copy kept anywhere. Once the page has loaded it keeps working with Wi‑Fi off.

## What it does

- **Photos** (JPG, PNG, WebP, HEIC in Safari): re-encoded at the quality you pick, large photos resized, location data removed. Save as the same format, JPG, WebP or PNG.
- **PDFs:** the pictures inside are recompressed; text stays sharp and selectable.
- **Videos** (MP4, MOV, WebM, MKV): re-encoded with the browser's built-in video hardware, saved as MP4, sound left untouched.
- Four squeeze levels (Light, Balanced, Max, Custom), before/after compare for photos, save one file or everything as a .zip.

## How it works

Everything runs client-side in plain HTML, CSS and JavaScript. There is no build step and no backend.

| Job | Done with |
| --- | --- |
| Images | Canvas API |
| PDFs | [pdf-lib](https://github.com/Hopding/pdf-lib) |
| Video | [Mediabunny](https://github.com/Vanilagy/mediabunny) on top of WebCodecs |
| Zip download | [JSZip](https://github.com/Stuk/jszip) |

The libraries load from public CDNs (cdnjs and jsDelivr). Fonts are Unbounded and Outfit from Google Fonts.

The hosted version uses [Vercel Web Analytics](https://vercel.com/docs/analytics) to count page visits. It sets no cookies and never sees your files.

## Run it locally

It is one file. Open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

## Deploy

On Vercel: import the repository, choose the **Other** framework preset, leave the build command empty, and deploy. Any static host (Netlify, GitHub Pages, Cloudflare Pages) works the same way.

## Browser support

Images and PDFs work in any modern browser. Video needs WebCodecs: recent Chrome, Edge and Safari.

## Contributing

Issues and pull requests are welcome. Fork it, change it, make it yours.

## License

[MIT](LICENSE) © 2026 Mohit Gupta, [guptamohit.com](https://guptamohit.com), [LinkedIn](https://www.linkedin.com/in/mohit9994)
