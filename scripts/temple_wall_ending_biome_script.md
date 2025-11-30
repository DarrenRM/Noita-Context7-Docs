---
title: Temple Wall Ending Biome Script
category: scripts
---

# Temple Wall Ending Biome Script

This script defines the behavior and elements for the "Temple Wall Ending" biome in Noita. It handles the loading of background elements, pixel scenes, and the spawning of the end portal.

## Core Functions

This biome primarily relies on two registered spawn functions:

*   **`init(x, y, w, h)`**: This function is called during the biome's initialization. It's responsible for loading visual assets and background elements.
*   **`spawn_endportal(x, y)`**: This function is specifically designed to spawn the end portal entity.

## Key Elements and Attributes

### `init(x, y, w, h)` Function Details

This function orchestrates the visual setup of the biome.

*   **Background Loading**:
    *   `LoadBackgroundSprite("data/biome_impl/temple/wall_background.png", x, y - 30, 35)`: Loads a background sprite, likely a decorative wall texture, positioned slightly above the biome's origin.
*   **Pixel Scene Loading**:
    *   `LoadPixelScene("data/biome_impl/temple/altar_top_ending.png", "data/biome_impl/temple/altar_top_visual.png", x, y-40, "", true)`: Loads a pixel scene representing an altar. It uses two image files for the main scene and its visual layer, positioned slightly above the origin.
    *   `LoadPixelScene("data/biome_impl/temple/solid.png", "", x, y-40+300, "", true)`: Loads a "solid" pixel scene, likely for structural elements or collision, positioned significantly higher than the origin.

### `spawn_endportal(x, y)` Function Details

This function is straightforward and handles the placement of the game's ending mechanism.

*   **Entity Spawning**:
    *   `EntityLoad("data/entities/buildings/teleport_ending.xml", x, y - 4)`: Spawns the `teleport_ending.xml` entity, which represents the end portal, slightly below the provided coordinates.

## Unused/Default Functions

The script includes numerous function definitions that are either empty or not actively used within this specific biome's logic. These are likely placeholders or inherited from a more general biome template.

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

This script relies on several external Lua files for its functionality:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`