---
title: Wand Level 03 - Procedural Generation
category: scripts
---

# Wand Level 03 - Procedural Generation

This script defines parameters for the procedural generation of wands, specifically targeting "Level 03" wands. It leverages the `gun_procedural_better.lua` script for core generation logic.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`60`**: This likely represents a base "power" or "level" value for the wand. Higher values generally lead to more complex and potent wands.
*   **`3`**: This parameter could influence the number of spell slots or the complexity of spell combinations allowed.
*   **`false`**: This boolean likely controls whether the wand generation is deterministic or randomized. `false` suggests a degree of randomness.

## Core Logic Reference

The actual generation mechanics are handled by the `gun_procedural_better.lua` script, which this file simply calls. For detailed information on how wands are constructed, refer to the documentation for that script.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural_better.lua")

generate_gun( 60, 3, false )
```