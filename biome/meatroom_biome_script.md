---
title: Meatroom Biome Script
category: biome
---

# Meatroom Biome Script

This script defines the behavior and content for the "Meatroom" biome in Noita. It handles the loading of the biome's visual scene and the spawning of specific entities.

## Core Functionality

### `init(x, y, w, h)`
This function is called when the Meatroom biome is initialized. It's responsible for loading the visual representation of the biome.

*   **`LoadPixelScene("data/biome_impl/meatroom.png", "", x, y, "", true)`**: Loads the pixel scene for the Meatroom biome from the specified PNG file. The other parameters control aspects like scene origin, rotation, and whether to use a specific material.

### `spawn_essence(x, y)`
This function is called to spawn specific entities within the Meatroom biome.

*   **`EntityLoad("data/entities/animals/boss_meat/boss_meat.xml", x, y)`**: Spawns the "boss_meat" entity, which is likely a unique enemy or boss associated with this biome.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation, indicating they are either placeholders for future development or not utilized in the current version of the Meatroom biome script.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_lamp(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`
*   `spawn_wands(x, y)`
*   `spawn_orb(x, y)`

## Constants

*   **`CHEST_LEVEL = 3`**: This constant likely indicates the default chest level associated with this biome, influencing the quality or type of chests that might spawn.

## Dependencies

This script relies on several other Lua files for its functionality:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/lib/utilities.lua`