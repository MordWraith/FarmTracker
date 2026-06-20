# Discord forum — first post (copy into `#plugins`)

**Title:** `FarmTracker`

**Tags:** `community`

---

## Paragraph post (same style as other plugin threads)

```
https://github.com/MordWraith/FarmTracker

Updated the GameHelper2 farm tracker: slim map/session overlays (centered on the XP bar), loot profit as divine equivalent from inventory changes, per-map history + session archive with frozen prices, map resume after disconnect, and DE/EN settings. Prices from poe2scout or poe.ninja + optional custom_prices.txt / metaArt.json (copy from LootTracker for rares).

v1.0.1: side zones like Abyssal Depths, Expedition sub-areas, and Breach domains now count as the same map run (one timer/profit row) — toggle "Treat sub-areas as same map" in settings (default on).

Also bundled in my Gamehelper releases (stable + experimental) — enable under Plugins.

Original plugin by Senbry — this repo is the GameHelper2 port. Read-only overlay, no automation.

Build from source: clone into Plugins/FarmTracker, dotnet build GameHelper + plugin. Tested on Gordin main and community forks (.NET 10, x64).

Feedback here; crashes/install → #help tag plugin.

Community third-party — use at your own risk.
```

---

## v1.0.1 thread update (short reply)

```
FarmTracker v1.0.1 — https://github.com/MordWraith/FarmTracker

Sub-areas (Abyssal Depths, Expedition side zones, Breach domains) now stay on the same map run instead of starting a new map counter. Setting: "Treat sub-areas as same map" (default on). Also in experimental Gamehelper catalog as 1.0.1.

Build from source as usual. Feedback in this thread.
```

---

## Forum template (structured)

**Author:** Senbry (GameHelper2 port: MordWraith)  
**Source:** https://github.com/MordWraith/FarmTracker  
**Also in:** [MordWraith/Gamehelper](https://github.com/MordWraith/Gamehelper) (stable + experimental)

### What it does

- Slim map/session overlays, loot profit (div equivalent), N/M/R/U kills
- Session archive, map resume, scout/ninja pricing
- **v1.0.1:** sub-areas count as same map run

### Install

**Option A:** [Gamehelper releases](https://github.com/MordWraith/Gamehelper) → enable FarmTracker  
**Option B:** clone into `Plugins/FarmTracker`, build GameHelper + plugin (see README)

### Disclaimer

Community third-party plugin. Use at your own risk.
