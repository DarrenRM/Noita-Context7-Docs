---
title: Wand Unshuffle 04 - Procedural Wand Generation
category: scripts
---

# Wand Unshuffle 04 - Procedural Wand Generation

This script defines parameters for generating a procedural wand in Noita. It leverages the `gun_procedural.lua` library to create wands with specific characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **80**: This likely represents a base "power" or "rarity" value for the wand. Higher values generally lead to more potent or rarer wands.
*   **4**: This parameter probably dictates the maximum number of spells that can be *drawn* from the wand's spell list.
*   **true**: This boolean likely enables or disables a specific feature related to spell shuffling or ordering within the wand. In this case, `true` suggests that the wand's spells will *not* be shuffled, maintaining their original order.

## Underlying Logic

The script relies on the `gun_procedural.lua` library for the actual generation process. This library handles:

*   Selecting spells based on rarity and available slots.
*   Determining wand properties like mana, recharge time, and projectile speed.
*   Applying modifiers and effects.

The specific values passed to `generate_gun` in this script are crucial for defining the characteristics of the wands produced by this particular generation method.