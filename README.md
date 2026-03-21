# RS3 Herb Run Tracker

A profit-tracking companion for herb runs in RuneScape 3. Works as a standalone webpage or as an [Alt1 Toolkit](https://runeapps.org/alt1) side-panel plugin.

![Alt1 Plugin](https://img.shields.io/badge/Alt1-Plugin-green) ![RuneScape 3](https://img.shields.io/badge/RuneScape-3-gold)

---

## Install in Alt1

Make sure [Alt1 Toolkit](https://runeapps.org/alt1) is running, then click:

```
alt1://addapp/https://jb-darnic.github.io/rs3-herb-run-tracker/appconfig.json
```

Or open that URL in your browser — Alt1 will prompt you to add the app.

**Manual install:** Open Alt1's built-in browser, navigate to `https://jb-darnic.github.io/rs3-herb-run-tracker/herb-run-guide.html`, and click the "Add App" button that appears.

---

## Use in a Browser

No install needed — just visit:

**https://jb-darnic.github.io/rs3-herb-run-tracker/herb-run-guide.html**

Works in any modern browser. All settings save to your browser's local storage.

---

## Features

### Patch Tracking
Track progress across all 9 herb patches: Prifddinas, Ardougne, Catherby, Falador, Morytania, Trollheim, Garden of Kharid, Wilderness, and Herblore Habitat. Each patch card shows teleport method, directions, and tags like quest requirements or disease-free status. Check off patches as you go, mark diseased patches, reorder via drag-and-drop, or disable patches you haven't unlocked.

### Profit Calculation
Select your primary herb from 7 options (Kwuarm, Spirit Weed, Harralander, Dwarf Weed, Lantadyme, Torstol, Arbuck) and see a full profit breakdown per run. The profit table accounts for seed cost, compost cost, Juju potion cost, disease risk, expected deaths, and Bloodweed from the Wilderness patch. Revenue and profit update in real time as you check off patches.

### Compost Selection
Choose between Ultracompost, Supercompost, or No Compost. Each has different costs, disease rates, and yield modifiers. The disease calculation uses actual growth-cycle math: `1 - (1 - diseasePerCycle)^4` across 4 growth cycles, so you see the true expected loss. Supercompost can actually be more profitable than Ultracompost for cheaper herbs — the table shows you exactly when.

### Garden of Kharid — Plant Power Seeds
Toggle Plant Power tiers 1–4 from the Garden of Kharid. Each tier adds extra seeds per patch and a yield bonus. The profit table adjusts seed costs and expected harvests automatically.

### Farming Unlock Toggles
Toggle the unlocks you have, and the effective yield updates in real time:

| Unlock | Effect |
|--------|--------|
| Magic Secateurs | ×1.10 yield multiplier |
| Juju Farming Potion | ×1.33 yield multiplier |
| Greenfingers Aura | +3% to +15% yield (5 tiers) |
| Master Farmer Outfit | ×1.07 yield multiplier |
| Farming Cape | ×1.05 yield multiplier |
| Scroll of Life | 10% chance to save seeds |
| Pharm Ecology Relic | Disease rate set to 0% |

Each toggle shows its RuneScape Wiki inventory icon for easy identification.

### Teleport Unlocks
Toggle fast teleports you've unlocked (Trollheim Farm Teleport, Mystical Sand Seed, Wilderness Sword 4) to adjust estimated run times for those patches.

### Run Timer
Start/pause a timer when you begin your run. Tracks elapsed time and calculates GP/minute when you finish. The timer persists if you switch tabs.

### Regrow Countdown
After completing a run, a countdown shows when your herbs will be ready for the next harvest (80 minutes standard, or faster with Speedy Growth from Garden of Kharid). Sends a browser notification (or Alt1 overlay alert) when herbs are ready.

### Run History
Completed runs are saved with profit, patch count, and timestamp. View your history with total runs, average profit, best run, and a sparkline chart of profit trends over time.

### Pre-Run Loadout
A checklist of everything you need before starting: seeds, secateurs, compost, teleport items, and optional items like Juju potion. Items update dynamically based on your compost and unlock selections. Check off items as you load your inventory.

### Live GE Prices
Fetch current Grand Exchange prices from the Weird Gloop API with one click. Updates herb prices, seed costs, and compost costs. In Alt1, prices auto-fetch when you open the panel.

### Themes & Display
Toggle between dark mode (default, earthy tones) and light mode (Farming Cape-inspired greens on warm parchment). Compact mode strips the view down to just patches, stats, and timer for an ultra-minimal overlay. Sound effects (herb-pick rustle and coin-clink chime) can be toggled on or off.

### Alt1 Panel Mode
When running inside Alt1, the layout automatically condenses to fit a ~390px side panel — smaller fonts, tighter spacing, bottom nav bar — without hiding any sections. Compact mode is still available from the bottom bar if you want an even smaller overlay.

---

## Settings Persistence

All settings are saved to `localStorage` and restored on reload:

- Selected herb, base yield, compost type, Plant Power tier
- Patch order, checked/diseased/disabled patches
- All farming unlock and teleport unlock toggles
- Compact mode, light mode, sound on/off
- Loadout checklist state
- Regrow countdown target
- Run history (stored separately, survives resets)

---

## Files

| File | Description |
|------|-------------|
| `herb-run-guide.html` | The full app — single self-contained HTML file with embedded CSS and JS |
| `appconfig.json` | Alt1 plugin manifest (app name, dimensions, permissions) |
| `icon.png` | 96×96 app icon for the Alt1 app list |
| `DEPLOY-ALT1.md` | Step-by-step deployment guide for hosting and Alt1 setup |
| `README.md` | This file |

---

## Updating

Push changes to the `main` branch. GitHub Pages redeploys automatically, and Alt1 loads the latest version from the URL each time the panel opens — no reinstall needed for users.

---

## Credits

Built for the RuneScape 3 community. Herb data, patch locations, and unlock mechanics sourced from the [RuneScape Wiki](https://runescape.wiki/). GE prices fetched from the [Weird Gloop API](https://api.weirdgloop.org/).

---

## License

Free to use, modify, and share. If you redistribute or fork, a link back to this repo is appreciated.
