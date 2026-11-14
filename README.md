# Scrunch

Shrink photos, PDFs and videos right in your browser. Nothing gets uploaded.

Scrunch is a single web page that compresses files on your own device. Drop in a batch of images, PDFs and videos, pick how hard to squeeze, and save the smaller files. No account, no server, no copy kept anywhere. Once the page has loaded it keeps working with Wi‑Fi off.

## Free, forever

Scrunch is free and will always be free. No paywall, no premium tier, no sign-up, no ads, no limits on how many files you squeeze. It is a side project made for fun, not a business, and it costs nothing to run because your own device does all the work.

## Runs 100% on your device

- Your files are opened, squeezed and saved inside your browser tab. They are never uploaded anywhere.
- There is no server that could receive a file, so there is nothing to store, sell or leak.
- Load the page, turn off Wi‑Fi, and it still works. That is the simplest way to check.
- Close the tab and everything is gone. Scrunch keeps no copy of anything.

## Privacy

- No account, no cookies, no tracking of what you compress.
- The hosted site counts anonymous page visits with [Vercel Web Analytics](https://vercel.com/docs/analytics). It never sees file names, file contents or anything you drop in.
- Photos have their location data (EXIF/GPS) removed when they are re-saved.
- The only things the page fetches from the internet are its own code libraries and fonts (see below), the same for every visitor.

## Open source

The full code is in this repository under the [MIT License](LICENSE). You can read exactly what it does, run your own copy, fork it, change it and share it, for free.

## What it does

- **Photos** (JPG, PNG, WebP, AVIF, HEIC): re-encoded at the quality you pick, large photos resized, location data removed. Save as the same format, JPG, WebP, AVIF or PNG. iPhone HEIC photos open in every browser.
- **Smart quality:** screenshots and graphics are spotted automatically and kept sharp; photos get the full squeeze.
- **PDFs:** the pictures inside are recompressed; text stays sharp and selectable.
- **Size limit:** pick "Files under" 500 KB, 1, 2 or 5 MB. Photos lower their quality, then their size, until they fit; PDFs step their pictures down. Videos are not affected.
- **File names** are tidied for upload forms (spaces and odd symbols become dashes) and end in `-scrunched`.
- When a batch finishes while you are in another tab, the tab title changes to "✓ Done".
- **Videos** (MP4, MOV, WebM, MKV): re-encoded with the browser's built-in video hardware, saved as MP4, sound left untouched.
- Four squeeze levels (Light, Balanced, Max, Custom), before/after compare for photos, save one file or everything as a .zip.
- Your last settings are remembered in your own browser (nothing is sent anywhere).

## How it works

Everything runs client-side in plain HTML, CSS and JavaScript. There is no build step and no backend.

| Job | Done with |
| --- | --- |
| Images | Canvas API, plus WebAssembly codecs loaded only when needed: [jSquash AVIF](https://github.com/jamsinclair/jSquash) for AVIF output and [heic-to](https://github.com/hoppergee/heic-to) (libheif) for HEIC outside Safari |
| PDFs | [pdf-lib](https://github.com/Hopding/pdf-lib) |
| Video | [Mediabunny](https://github.com/Vanilagy/mediabunny) on top of WebCodecs |
| Zip download | [JSZip](https://github.com/Stuk/jszip) |

The libraries load from public CDNs (cdnjs and jsDelivr). Fonts are Unbounded and Outfit from Google Fonts.

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

## Made by

Designed and built by **Mohit Gupta**, a product designer in Toronto.

- Portfolio: [guptamohit.com](https://guptamohit.com)
- LinkedIn: [linkedin.com/in/mohit9994](https://www.linkedin.com/in/mohit9994)
- Live site: [scrunch.guptamohit.com](https://scrunch.guptamohit.com)

## License

[MIT](LICENSE) © 2026 Mohit Gupta. Free to use, copy, change and share.
