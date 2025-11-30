---
title: Ending Placeholder Biome Script
category: scripts/
---

# Ending Placeholder Biome Script

This script defines the behavior and entities for a placeholder biome used in the game Noita, likely for testing or as a final area. It focuses on loading a specific pixel scene and spawning a key entity.

## Core Functionality

### `init(x, y, w, h)`

This function is the primary initialization routine for the biome.

*   **`EntityLoad("data/entities/misc/music_energy_050.xml", x, y)`**: Loads a music entity, likely to set the ambiance for this area.
*   **`LoadPixelScene("data/biome_impl/ending_placeholder.png", "", x, y, "", true)`**: Loads the visual representation of the biome from a PNG file. This defines the terrain and static elements.

### `spawn_endcrystal(x, y)`

This function is responsible for spawning a specific, important entity within the biome.

*   **`EntityLoad("data/entities/buildings/endcrystal.xml", x, y)`**: Loads the `endcrystal` entity, which is likely a central object or objective within this placeholder ending.

## Spawn Functions (Placeholder)

The following functions are defined but are empty. They represent potential hooks for spawning various elements, but in this specific script, they are not implemented. This suggests the biome is intended to be minimal or that these spawns are handled elsewhere.

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

## Constants

*   **`CHEST_LEVEL = 3`**: This constant might indicate a default chest rarity or level associated with this biome, though no chests are explicitly spawned by this script.

## Dependencies

*   `dofile_once("data/scripts/director_helpers.lua")`
*   `dofile_once("data/scripts/biome_scripts.lua")`
*   `dofile_once("data/scripts/lib/utilities.lua")`