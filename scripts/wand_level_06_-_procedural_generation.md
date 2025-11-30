---
title: Wand Level 06 - Procedural Generation
category: scripts
---

# Wand Level 06 - Procedural Generation

This script defines parameters for the procedural generation of wands found at level 06 in Noita. It leverages the `gun_procedural_better.lua` script to create these wands.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`120`**: This likely represents a base "power" or "rarity" value for the wands generated at this level. Higher values generally lead to more complex and powerful wands.
*   **`6`**: This number probably dictates the maximum number of spell slots available on the generated wands.
*   **`false`**: This boolean value might control whether certain advanced or experimental generation features are enabled. `false` suggests these features are disabled for this level.

## Underlying Logic

The core functionality is handled by `gun_procedural_better.lua`. This external script contains the algorithms and rules for combining spell components, determining wand properties (like mana, recharge time, spell count), and assigning them to different in-game levels. The parameters passed in this script fine-tune the output of that more general generation system for level 06.