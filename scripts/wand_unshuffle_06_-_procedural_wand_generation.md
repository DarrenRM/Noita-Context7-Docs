---
title: Wand Unshuffle 06 - Procedural Wand Generation
category: scripts
---

# Wand Unshuffle 06 - Procedural Wand Generation

This script defines parameters for generating a procedural wand in Noita. It utilizes the `gun_procedural.lua` library to create wands with specific characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`120`**: This likely represents a base "power" or "complexity" value for the wand. Higher values generally lead to more complex and potentially more powerful wands.
*   **`6`**: This parameter probably dictates the maximum number of spells that can be *drawn* from the wand's spell list in a single cast.
*   **`true`**: This boolean flag likely enables or disables a specific feature related to wand generation, possibly related to spell shuffling or the order in which spells are selected.

## Underlying Logic (from `gun_procedural.lua`)

While the specific implementation details are in `gun_procedural.lua`, the `generate_gun` function typically handles:

*   **Spell Selection**: Choosing spells from the game's available pool based on various criteria (rarity, type, synergy).
*   **Modifier Application**: Adding modifiers to spells (e.g., faster casting, increased damage, projectile behavior changes).
*   **Stat Assignment**: Determining wand stats like mana, recharge time, cast delay, and spell slots.
*   **Procedural Generation**: Ensuring a degree of randomness and uniqueness in each generated wand.

## Example Usage (within the game's context)

This script would be executed by Noita's game engine during world generation or when a specific wand is intended to be created. The values passed to `generate_gun` directly influence the resulting wand's properties and capabilities.