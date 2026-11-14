# Security

Scrunch is a static web page. There is no server, no database, no login and no file upload, so there is very little to attack. Your files are processed inside your own browser tab and never sent anywhere.

## What protects the site

- **Locked-down network access.** A Content Security Policy (set in `vercel.json`) only lets the page load code from itself and two pinned public CDNs (cdnjs and jsDelivr) and fonts from Google Fonts. The page may only send data back to its own address, so even a misbehaving library could not post your files to some other server.
- **Can't be framed.** Other sites can't embed Scrunch in a hidden frame to trick people into clicking things (`frame-ancestors 'none'`, `X-Frame-Options: DENY`).
- **No extra device access.** Camera, microphone, location, payment and similar browser features are switched off for the page.
- **HTTPS only**, with strict transport security.
- **Pinned library versions.** JSZip 3.10.1, pdf-lib 1.17.1, Mediabunny 1.61.0, jSquash AVIF 2.1.1 (with wasm-feature-detect 1.8.0) and heic-to 1.6.7 are loaded by exact version, never "latest". The AVIF and HEIC codecs are WebAssembly and only load when you use them; the policy allows WebAssembly to run but still blocks any other code from outside these sources.
- **Only the owner can change the live site.** Forks and pull requests from other people never deploy to scrunch.guptamohit.com; only changes merged into `main` by the owner do.

## Reporting a problem

If you find a security issue, please don't open a public issue. Use GitHub's **Report a vulnerability** button on this repository's Security tab, or contact Mohit Gupta through [guptamohit.com](https://guptamohit.com).
