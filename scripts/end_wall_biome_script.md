---
title: End Wall Biome Script
category: scripts
---

# End Wall Biome Script

This script defines the behavior and content for the "End Wall" biome in Noita. It acts as a fallback biome, providing a basic structure and occasional special elements when a more specific biome cannot be determined.

## Core Functionality

The script registers itself as a default biome function using `RegisterSpawnFunction`. It then defines a series of placeholder functions for spawning various entities and elements, most of which are not implemented in this specific script. The primary logic resides within the `init` function.

### `init(x, y, w, h)`

This function is called when the End Wall biome is initialized. It sets a random seed and then conditionally loads different "altar top" pixel scenes based on a random number. This allows for some visual variation in the biome.

*   **`SetRandomSeed(x, y)`**: Initializes the random number generator based on the biome's coordinates.
*   **`Random(1, 50)`**: Generates a random integer between 1 and 50.
*   **Conditional `LoadPixelScene`**: Based on the random number, different pixel scenes (representing various liquid or elemental altars) are loaded. If none of the specific conditions are met, a default `altar_top.png` is loaded.
*   **`LoadPixelScene("data/biome_impl/temple/solid.png", "", x, y-40+300, "", true)`**: Loads a solid structure, likely forming the base of the biome.

### `spawn_portal(x, y)`

This function is responsible for spawning the end-of-level portal.

*   **`EntityLoad("data/entities/buildings/teleport_end_wall.xml", x, y)`**: Loads the `teleport_end_wall.xml` entity, which represents the portal.

## Unimplemented Spawn Functions

The following functions are defined but do not contain any implementation in this script. They are likely intended as placeholders for future development or for use by other biome scripts that might inherit or call them.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`

## Dependencies

This script relies on several helper files:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`