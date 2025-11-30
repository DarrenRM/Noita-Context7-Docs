---
title: Wand Level 03 Procedural Generation
category: scripts
---

# Wand Level 03 Procedural Generation

This script defines the parameters for generating a procedural wand at level 03 in Noita. It utilizes the `generate_gun` function from `gun_procedural.lua` to create the wand with specific characteristics.

## Key Parameters

The `generate_gun` function is called with the following arguments:

*   **`60`**: This likely represents the base spell count or a similar attribute influencing the wand's power or complexity.
*   **`3`**: This value could indicate the wand's level or a specific tier of procedural generation.
*   **`false`**: This boolean likely controls whether the wand is guaranteed to have a specific property, such as being a "special" wand or having a particular modifier.

## Underlying Logic

The core functionality is handled by the `generate_gun` function, which is defined in `data/scripts/gun/procedural/gun_procedural.lua`. This function is responsible for:

*   Selecting spells from a predefined pool.
*   Determining the order and combination of spells.
*   Assigning modifiers and properties to the wand.
*   Setting the wand's visual and functional attributes.

The specific values passed to `generate_gun` in this script (`60`, `3`, `false`) tailor the output to create a wand appropriate for level 03 progression in the game.