---
title: Wand Level 02 - Procedural Generation
category: scripts/gun/procedural
---

# Wand Level 02 - Procedural Generation

This script defines parameters for generating a "better" wand at level 02 during procedural generation in Noita. It leverages a shared procedural generation script for core functionality.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`40`**: This likely represents a base "power" or "rarity" value for the wand. Higher values generally lead to more potent or rarer wands.
*   **`2`**: This parameter probably influences the number of spell slots or the complexity of the wand's spell arrangement.
*   **`false`**: This boolean likely controls whether the wand is guaranteed to have a specific, pre-defined spell or if it's entirely procedurally generated. `false` suggests a fully procedural outcome.

## Core Functionality

This script relies on `data/scripts/gun/procedural/gun_procedural_better.lua` for the actual generation logic. This external script handles the complex task of combining spells, modifiers, and wand properties to create a functional and balanced wand.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural_better.lua")

generate_gun( 40, 2, false )
```