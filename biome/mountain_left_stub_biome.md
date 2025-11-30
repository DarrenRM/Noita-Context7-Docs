---
title: Mountain Left Stub Biome
category: biome
---

---

# Mountain Left Stub Biome

This document describes the `mountain_left_stub.lua` script, which defines a specific biome segment within the Noita game, likely serving as an entry point or transition area in the mountain region.

## Core Functionality

This script registers a biome initialization function that loads pixel scenes to construct the visual and physical layout of the biome.

### Key Functions

*   **`init(x, y, w, h)`**: This is the primary function called when the biome is initialized. It's responsible for loading the visual elements of the biome.
    *   `LoadPixelScene("data/biome_impl/mountain/left_stub.png", "", x, y, "data/biome_impl/mountain/left_stub_background.png", true)`: Loads the main visual layer and background for the left stub section of the mountain biome.
    *   `LoadPixelScene("data/biome_impl/mountain/left_entrance_below.png", "", x+512, y, "data/biome_impl/mountain/left_entrance_below_background.png", true)`: Loads an additional visual layer and background, positioned to the right of the main stub, likely representing a lower entrance or connected area.

### Initialization

*   **`RegisterSpawnFunction(0xffffeedd, "init")`**: This line registers the `init` function to be called at a specific point during the game's initialization process, identified by the hexadecimal value `0xffffeedd`.

### Unused/Default Functions

*   **`spawn_wands(x, y)`**: This function is defined but empty, indicating that wand spawning for this specific biome segment is handled elsewhere or not intended for this stub.

## Dependencies

*   **`dofile_once("data/scripts/director_helpers.lua")`**: Imports utility functions for managing game directors and biome placement.
*   **`dofile_once("data/scripts/biomes/mountain/mountain.lua")`**: Imports core definitions and functions related to the mountain biome.

## Constants

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or rarity of chests that can spawn within this biome or connected areas.