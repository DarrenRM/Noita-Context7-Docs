---
title: Wand Unshuffle 05 - Procedural Wand Generation
category: scripts
---

# Wand Unshuffle 05 - Procedural Wand Generation

This script defines parameters for generating a procedural wand in Noita. It utilizes the `gun_procedural.lua` library to create wands with specific characteristics.

## Key Generation Parameters

The `generate_gun` function is called with the following arguments:

*   **`100`**: This likely represents the **maximum number of spells** the wand can hold.
*   **`5`**: This value could indicate the **maximum number of spell charges** the wand starts with.
*   **`true`**: This boolean likely controls whether the wand has **randomized spell order** (unshuffled).

## Core Functionality

The script's primary purpose is to leverage the `generate_gun` function from `gun_procedural.lua` to produce a wand. The specific values passed to `generate_gun` dictate the wand's capacity and charge count, while the `true` parameter ensures its spells are not in a fixed, predictable order.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")

generate_gun( 100, 5, true )
```