# AnimalDex

A Pokédex-style animal encyclopedia for kids, inspired by the Johto Pokédex — built as a single-file, vanilla HTML/CSS/JS web app that emulates a physical handheld device.

**🌐 Live app:** **[sharath-chandr.github.io/animalDex](https://sharath-chandr.github.io/animalDex/)**

**📱 Download the Android app:** **[Click here to download AnimalDex.apk](https://sharath-chandr.github.io/animalDex/AnimalDex.apk)** — open this link on your phone, then tap the downloaded file to install (allow "install unknown apps" for your browser when prompted). It's a native wrapper around the same app with proper camera support.

## How it works

- The on-screen "device" is display-only — every interaction goes through the physical D-pad / A / B / Menu buttons below the screen.
- **Camera** — live feed via `getUserMedia`, with a scanning crosshair.
- **A (scan)** — captures the frame and sends it to the Claude API (`claude-opus-5`) for identification, returning name / type / habitat / a fun fact / extended info as structured JSON.
- **No API key set?** Falls back to sample data featuring Indian wildlife (Indian Peafowl, Bengal Tiger, King Cobra, Asian Elephant, Red Panda).
- Discovered animals persist in the browser via `localStorage`.
- Tap **⚙ API key** below the device to add your own [Anthropic API key](https://console.anthropic.com/) for live recognition — it's stored only in your browser and sent directly to `api.anthropic.com`, never to any server this app controls.

## Files

- `index.html` — the entire app (no build step, no dependencies beyond a Google Fonts stylesheet).
- `AnimalDex.apk` — a native Android wrapper (WebView-based) for installing as a standalone app on Android. Sideload it directly (enable "install unknown apps" for your browser/file manager).

## Tech

Vanilla JS/CSS, no frameworks. Camera via `getUserMedia`, speech via `speechSynthesis`, AI vision via the Anthropic Messages API called directly from the browser.
