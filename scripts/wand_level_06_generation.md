---
title: Wand Level 06 Generation
category: scripts
---

# Wand Level 06 Generation

This script defines the procedural generation parameters for a Wand of Level 06 in Noita. It utilizes the `generate_gun` function from `gun_procedural.lua` to create the wand with specific attributes.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`120`**: This likely represents a base "power" or "rarity" value for the wand. Higher values generally lead to more potent or rarer wands.
*   **`6`**: This number typically corresponds to the "wand level" or "tier" of the wand being generated. Level 6 wands are mid-to-late game items.
*   **`false`**: This boolean value likely controls whether the wand is guaranteed to have a specific, pre-defined set of spells or if it's purely procedurally generated with random spell combinations. `false` suggests a more randomized outcome.

## Underlying Logic

The `generate_gun` function, as defined in `data/scripts/gun/procedural/gun_procedural.lua`, handles the complex logic of:

*   **Spell Selection**: Determining which spells are available to be placed on the wand based on its level and rarity.
*   **Spell Ordering**: Arranging the selected spells in a functional and often synergistic order.
*   **Modifier Application**: Adding modifiers (like increased damage, faster casting, etc.) to spells or the wand itself.
*   **Stat Calculation**: Assigning base stats such as mana, recharge time, cast delay, and projectile speed.

This specific call to `generate_gun( 120, 6, false )` indicates the creation of a Level 06 wand with a moderate power level and a high degree of procedural randomness in its spell composition.