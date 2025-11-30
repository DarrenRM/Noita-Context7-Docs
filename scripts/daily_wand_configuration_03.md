---
title: Daily Wand Configuration (03)
category: scripts
---

# Daily Wand Configuration (03)

This script configures a specific daily wand for Noita, leveraging the `generate_daily_wand` function.

## Wand Generation Parameters

The `generate_daily_wand` function is called with the following parameters:

*   **`60`**: This likely represents the **base spell count** for the wand.
*   **`3`**: This parameter probably dictates the **number of spell slots** available on the wand.
*   **`false`**: This boolean value could indicate whether the wand is **limited** or has other special properties.

## Related Functions

This script utilizes the `generate_daily_wand` function, which is defined in `data/scripts/gun/procedural/wand_daily.lua`.

The commented-out line `-- generate_gun( 40, 2, false )` suggests that a similar function, `generate_gun`, might exist for generating more general-purpose wands with different parameters (40 base spell count, 2 spell slots).