# dsh-skin-pixel-anime

[中文](#功能) · A pixel-anime skin plugin for [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) web UI.

## Features

- **Pixel clock** — SVG-drawn LED readout in the conversation header, with blinking colon, sparkle, and heart. Stands down automatically if the host build already draws its own hero clock.
- **Five palettes** — Matrix / Sakura / Ocean / Sunset / Vapor, each with tuned light and dark schemes that follow the host Appearance setting.
- **Five pixel fonts + system default** — VT323, Press Start 2P, Silkscreen, Pixelify Sans, and Fusion Pixel (simplified Chinese, pixelates CJK text too). All fonts are embedded — no network requests, offline-friendly. Latin-only faces fall back to system fonts for Chinese.
- **Corner presets** — square / soft (2px) / round (8px), applied across every UI element.
- **CRT scanline + pixel-dither overlays** — subtle, pointer-transparent, disabled under `prefers-reduced-motion`.
- **Settings tab** — everything above is configurable in Settings → Plugins → Pixel Anime. Choices apply instantly and persist in browser localStorage.

## Install

From the [dsh-market](https://github.com/dsh-market/dsh-market) plugin marketplace (设置 → 插件市场, recommended — installs the prebuilt tarball), or via a local-directory install (插件管理 → 本地插件目录) pointing at a clone of this repo or an unpacked release tarball.

Requires a DSH web host with client bundle support (0.1.0-rc.6+). Refresh the page after install.

## Structure

Hand-authored against the loader's closure-factory contract — no build step:

- `lib/index.js` — host half (marker plugin for the bundle patch row)
- `lib/client.js` — client half: token overrides, stylesheet, clock, settings tab
- `cordis.patch.yml` — bundle patch row
- `OFL.txt` — license notices for the embedded fonts (all SIL OFL 1.1)

## License

MIT for the plugin code. Embedded fonts are licensed under the SIL Open Font License 1.1 — see [OFL.txt](OFL.txt) for each font's copyright notice.
