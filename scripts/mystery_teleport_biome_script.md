---
title: Mystery Teleport Biome Script
category: scripts/
---

# Mystery Teleport Biome Script

This script defines the behavior and content for the "Mystery Teleport" biome in Noita. It handles the loading of the biome's visual elements and the spawning of specific entities.

## Core Functionality

The script registers two primary spawn functions:

*   `init`: Called when the biome is initialized.
*   `spawn_essence`: Called to spawn the core entity of this biome.

## Key Functions

### `init(x, y, w, h)`

This function is responsible for loading the visual assets of the Mystery Teleport biome.

*   **`LoadPixelScene( "data/biome_impl/mystery_teleport.png", "", x, y, "data/biome_impl/essenceroom_background.png", true )`**: This is the core of the `init` function. It loads two pixel scenes:
    *   `data/biome_impl/mystery_teleport.png`: The primary visual layer for the biome.
    *   `data/biome_impl/essenceroom_background.png`: A background layer.
    *   `x`, `y`: The coordinates where the scene will be loaded.
    *   `true`: Indicates that the background should be loaded.

### `spawn_essence(x, y)`

This function is responsible for spawning the main entity that defines the Mystery Teleport biome.

*   **`EntityLoad( "data/entities/buildings/mystery_teleport.xml", x, y )`**: Loads the `mystery_teleport.xml` entity at the specified `x`, `y` coordinates. This entity likely contains the logic and appearance of the teleport itself.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or remnants from a more general biome script template.

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
*   `spawn_orb(x, y)`