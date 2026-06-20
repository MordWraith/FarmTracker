# FarmTracker

Community plugin for [GameHelper2](https://github.com/Gordin/GameHelper2) (Path of Exile 2).

Tracks **farm sessions** live: slim map/session overlays, kill counts (N/M/R/U), **loot profit** in divine equivalent (inventory diff), per-map history, and archived sessions with frozen prices. Prices from **poe2scout** / **poe.ninja** plus optional `custom_prices.txt` and `metaArt.json`.

Originally by **Senbry**; GameHelper2 port maintained by **MordWraith**. Concept inspired by PoeFixer FarmCounter — read-only overlay (**build from source**).

Also bundled in [MordWraith/Gamehelper](https://github.com/MordWraith/Gamehelper) releases (stable + experimental).

## Features

- **Slim overlay** — auto mode: map strip on maps (area, timer, profit, kills), session strip in town/hideout (maps, time, div/h)
- **XP bar anchor** — centered on the experience bar (or custom screen position)
- **Loot profit** — inventory diff (main inventory, currency tab, endgame splinters); values in **divine equivalent**, not raw divines only
- **Settings tabs** — Session (map table + loot), Loot, Archive (details/delete), Prices
- **Map resume** — continues a map run after reconnect (AreaHash)
- **Session archive** — frozen prices per archived session (`sessions/*.json`)
- **Prices** — poe2scout or poe.ninja, league selector, refresh interval, `custom_prices.txt`
- **Sub-areas** — Abyssal Depths, Expedition side zones, Breach domains count as the **same map run** (toggle in settings, default on)
- **DE/EN** — settings and overlay strings via GameHelper localization

## Requirements

- A working [GameHelper2](https://github.com/Gordin/GameHelper2) source tree (plugin, not a standalone app)
- **.NET 10 SDK** (`net10.0-windows`, x64)
- Tested on upstream **`main`** and [MordWraith/Gamehelper](https://github.com/MordWraith/Gamehelper) (June 2026)

Also compatible with maintained forks on the same plugin API / `net10.0-windows` target.

## Build & install

1. Clone GameHelper2 and this repo:

   ```bash
   git clone https://github.com/Gordin/GameHelper2.git
   cd GameHelper2
   git clone https://github.com/MordWraith/FarmTracker.git Plugins/FarmTracker
   ```

2. Build GameHelper once, then the plugin:

   ```bash
   dotnet build GameHelper/GameHelper.csproj -c Release
   dotnet build Plugins/FarmTracker/FarmTracker.csproj -c Release
   ```

   Post-build copies `FarmTracker.dll`, `custom_prices.txt`, and `metaArt.json` to  
   `GameHelper/bin/Release/net10.0-windows/win-x64/Plugins/FarmTracker/`.

3. Run GameHelper → **Plugins** → enable **FarmTracker**.

### Config folder (runtime)

| Path | Purpose |
|------|---------|
| `Plugins/FarmTracker/config/settings.txt` | Overlay, prices, timers (JSON) |
| `Plugins/FarmTracker/custom_prices.txt` | Manual prices (`ItemName=divine` per line) |
| `Plugins/FarmTracker/metaArt.json` | Item basename → display name (copy full file from [LootTracker](https://github.com/yokkenUA/LootTracker) for best coverage) |
| `Plugins/FarmTracker/price_cache.json` | Cached scout/ninja prices (auto) |
| `Plugins/FarmTracker/sessions/` | Archived sessions (`session_*.json`) |

Shipped `metaArt.json` is `{}` — currency items work out of the box; copy LootTracker's `metaArt.json` for rare/uniques.

## Loot & profit note

Profit is **estimated loot value in div** (chaos/exalts/etc. converted via API rates), shown with one decimal in the overlay. Loot is detected by **inventory changes**, not ground labels. Tracking runs on **maps**; hideout/town show session totals only.

## Credits

- Plugin author: **Senbry**
- GameHelper2 port: **MordWraith**
- [GameHelper2](https://github.com/Gordin/GameHelper2) (Gordin / community)
- `metaArt.json` format from [yokkenUA/LootTracker](https://github.com/yokkenUA/LootTracker)
- Concept inspiration: PoeFixer FarmCounter (not affiliated)

## Disclaimer

Third-party plugin — **use at your own risk**. Read-only overlay; no input automation. Comply with GGG terms of service.

## Support

- **This plugin:** Discord `#plugins` forum thread
- **GameHelper install/crashes:** `#help` with tag **`plugin`**

## Version history

| Version | Notes |
|---------|--------|
| **1.0.1** | Sub-areas (Abyss_*, ExpeditionSubArea_*, BreachDomain_*) stay on the same map run; setting `TreatSubAreasAsSameMap` (default on) |
| **1.0.0** | Slim XP-bar overlays, session/map/archive UI, map resume, frozen archive prices, scout/ninja + metaArt pricing |
