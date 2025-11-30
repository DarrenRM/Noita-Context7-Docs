---
title: Daily Wand Configuration (05)
category: scripts
---

# Daily Wand Configuration (05)

This script defines a specific configuration for a daily wand in Noita, leveraging the `generate_daily_wand` function.

## Core Function

The primary function used is `generate_daily_wand`.

### `generate_daily_wand( mana, shuffle, always_cast )`

*   **`mana`**: (Number) The base mana pool for the wand.
*   **`shuffle`**: (Boolean) Whether the wand's spell order is shuffled.
*   **`always_cast`**: (Boolean) If true, the wand will always attempt to cast its spells, even if it has insufficient mana.

## Configuration Details

This specific daily wand is generated with the following parameters:

*   **Mana**: `100`
*   **Shuffle**: `5` (This value likely represents a specific shuffle behavior or seed, as the standard `generate_daily_wand` expects a boolean for shuffle. This might be an internal detail of `generate_daily_wand` or a custom implementation.)
*   **Always Cast**: `false`

## Notes

*   The commented-out line `generate_gun( 40, 2, false )` suggests this script might be a variation or evolution of a more general gun generation function, but it is not active in this configuration.
*   The exact behavior of `shuffle = 5` would depend on the implementation of `generate_daily_wand` in `data/scripts/gun/procedural/wand_daily.lua`.