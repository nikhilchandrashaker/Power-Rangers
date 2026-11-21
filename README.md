# ⚡ Power Rangers Analytics

An interactive dashboard that ranks 161 Power Rangers entries and picks the best ranger for each color.

**Live page:** https://claude.ai/artifact/2kRwHEkfvavQCQNFGY28x6
**Source:** `power-rangers-analytics.html` (single self-contained file, no dependencies)

## What it does

- Scores every ranger on five criteria and ranks them overall.
- Shows the top-scoring ranger for each color (Red, Blue, Yellow, Pink, Green, Black, White, Gold, Silver, Purple, Orange, and Dark).
- Lets you change how much each criterion matters with sliders. The ranking and color winners update live.
- Has a search box for filtering by name, season, or color.

## Scoring

Each ranger gets a 1–10 rating on:

| Criterion | What it covers |
|---|---|
| Combat | Fighting ability and power level |
| Leadership | Command, strategy, team role |
| Arsenal | Weapons, Zords, and upgrades |
| Arc | Character development and story |
| Iconic | Fan impact and cultural footprint |

The overall score is a weighted average. Default weights are Combat 3, all others 2. Setting a weight to 0 removes that criterion.

**These ratings are subjective opinion, not official stats.** Ratings for lesser-known rangers are rough placeholders.

## Coverage

- Every US season from Mighty Morphin through Cosmic Fury.
- Main teams, Sixth/Gold/Silver rangers, and major extras.
- **Dark** is its own category for evil or corrupted rangers (Dark Rangers, Psycho Rangers, Shadow Rangers, A-Squad, Heckyl, evil avatars, and similar).
- Shades are grouped under the base color (Crimson → Red, Navy and Aqua → Blue, Mercury → Silver).
- Teams like the Shadow Rangers, A-Squad, and Evil Grid Battleforce Rangers are single entries.

**Not included:** comic-only rangers, spin-offs, cameos, and a few temporary cases (controlled Galaxy Rangers, Lightspeed's Cyborg Rangers). Roxy and Blaze (Beast Morphers) never morphed as heroes, so only their evil avatars appear.

## Data accuracy

Rosters for Turbo, Ninja Steel, Dino Charge, Beast Morphers, Dino Fury, Cosmic Fury, and the Sixth Rangers were checked against wiki sources. Other seasons are from memory and may contain errors.

## Editing the data

All data lives in one block in the HTML file, one line per season:

```
Season Name:Ranger Name|Color|code;Ranger Name|Color|code
```

The `code` is five characters, one per criterion in this order: **Combat, Leadership, Arsenal, Arc, Iconic**. Digits 1–9 are scores, and `A` means 10. Example: `8988A` is Combat 8, Leadership 9, Arsenal 8, Arc 8, Iconic 10.

To add a ranger, append `;Name|Color|code` to the right season line, or add a new season line. Colors must match a key in the `C` object near the top of the script (add a new key there for a new color).

## Ideas for later

- Verify the remaining seasons against sources.
- Add comic-only and legendary rangers.
- Head-to-head compare mode.
- Per-season and per-color filters.
