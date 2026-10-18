# atdx.github.io

**WARP WireGuard Config Generator** — https://atdx.github.io/

A browser-based tool that generates WireGuard configurations for Cloudflare WARP, entirely client-side: keypair generation, WARP registration, QR code for mobile import, and `.conf` download.

Based on [lanrat/wireguard-warp-generator](https://github.com/lanrat/wireguard-warp-generator).

## Files

| File | Description |
| --- | --- |
| `index.html` | UI and application logic |
| `wireguard.js` | WireGuard (Curve25519) keypair generation — from [WireGuard tools](https://git.zx2c4.com/wireguard-tools/) by Jason A. Donenfeld, GPL-2.0 |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll build) |

## How it works

1. Generates a WireGuard keypair locally in your browser.
2. Registers the public key with Cloudflare's WARP API (via CORS proxy `proxy.corsfix.com`).
3. Outputs a complete WireGuard configuration plus a QR code.

The private key is generated locally and never transmitted anywhere; only the public key is sent to Cloudflare.

## Local preview

Serve this folder with any static file server, e.g.:

```sh
npx serve .
```

or open `index.html` directly in a browser.

## Credits

- Original project: [lanrat/wireguard-warp-generator](https://github.com/lanrat/wireguard-warp-generator)
- `wireguard.js`: Jason A. Donenfeld (WireGuard tools, GPL-2.0)
