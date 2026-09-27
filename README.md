# dsh-skin-pixel-anime

[中文](#功能) · A pixel-anime skin plugin for [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) web UI.

## Features

- **Pixel clock** — SVG-drawn LED readout in the conversation header, with blinking colon, sparkle, and heart. Stands down automatically if the host build already draws its own hero clock.
- **Five palettes** — Matrix / Sakura / Ocean / Sunset / Vapor, each with tuned light and dark schemes that follow the host Appearance setting.
- **Four layered text schemes** — Ink / Phosphor / Blueprint / Amber. Each one sets a full ladder of text tones (primary → secondary → tertiary → caption → dimmed) plus link, brand text, and markdown code-area colors, so headings, body, metadata, and links read at distinct depths on top of any palette.
- **Five pixel fonts + system default** — VT323, Press Start 2P, Silkscreen, Pixelify Sans, and Fusion Pixel (simplified Chinese, pixelates CJK text too). All fonts are embedded — no network requests, offline-friendly. Latin-only faces fall back to system fonts for Chinese.
- **Corner presets** — square / soft (2px) / round (8px), applied across every UI element.
- **Rotating pixel starfield** — 42 rainbow stars with LED-style stepped twinkle, plus a milky way simulated purely with stars: a tight Gaussian core band and a wider halo band along one axis. The whole sky sits in a layer that rotates once every 8 minutes. No gradients — every star is a square pixel, deterministic across reloads.
- **Meteors, bursts, and fireballs** — a solo streak every 20–30 s (one in ten is an 8px warm-hued fireball with a pixel halo), and every so often a 10-second shower burst rains parallel meteors from a single radiant in a shared hue family. Burst cadence (rare/standard/often), meteors per burst (20/35/55), and fireball chance (off/5%/10%/25%) are user-configurable.
- **CRT scanline + pixel-dither overlays** — subtle, pointer-transparent, disabled under `prefers-reduced-motion`.
- **Settings tab** — palettes, text schemes, corners, fonts, background motion on/off, and all meteor parameters live in Settings → Plugins → Pixel Anime. Choices apply instantly (the meteor scheduler reads the latest choices at fire time, no reload needed) and persist in browser localStorage.

## Install

From the [dsh-market](https://github.com/dsh-market/dsh-market) plugin marketplace (设置 → 插件市场, recommended — installs the prebuilt tarball), or via a local-directory install (插件管理 → 本地插件目录) pointing at a clone of this repo or an unpacked release tarball.

Requires a DSH web host with client bundle support (0.1.0-rc.6+). Refresh the page after install.

## Structure

Hand-authored against the loader's closure-factory contract — no build step:

- `lib/index.js` — host half (marker plugin for the bundle patch row)
- `lib/client.js` — client half: token overrides, stylesheet, clock, rotating starfield, meteors, settings tab
- `cordis.patch.yml` — bundle patch row
- `OFL.txt` — license notices for the embedded fonts (all SIL OFL 1.1)

## License

MIT for the plugin code. Embedded fonts are licensed under the SIL Open Font License 1.1 — see [OFL.txt](OFL.txt) for each font's copyright notice.
