---
title: Bridge Biome Script
category: scripts/
---

# Bridge Biome Script

This script defines the behavior and spawning logic for the "Bridge" biome in Noita. It primarily handles loading the visual representation of the biome and registering functions for entity spawning.

## Core Biome Logic

The script registers two primary spawn functions:

*   `init`: Called when the biome is initialized.
*   `spawn_bridge`: Called to handle specific bridge-related spawning.

### `init(x, y, w, h)`

This function is responsible for loading the visual assets of the bridge biome.

*   **`LoadPixelScene("data/biome_impl/spliced/bridge.png", "", x, y, "", true)`**: Loads the pixel scene data from `bridge.png` at the specified coordinates `x`, `y`. This defines the terrain and visual layout of the bridge.

## Entity Spawning Functions

The script includes numerous placeholder functions for spawning various entities. These are often called by the game's director system but are not implemented within this specific script, indicating that their logic resides elsewhere or is handled by the biome's pixel scene definition.

### Implemented Spawning:

*   **`spawn_bridge(x, y)`**: This function is commented out but indicates that the bridge structure itself is intended to be spawned via an XML definition (`physics_suspension_bridge_spawner.xml`).

### Unimplemented/Placeholder Spawning Functions:

The following functions are defined but have empty bodies, meaning they do not perform any actions within this script. Their intended functionality is likely handled by other game systems or biome definitions.

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
*   `spawn_wands()`

## Dependencies

This script relies on external Lua files for core Noita functionality:

*   `dofile_once("data/scripts/director_helpers.lua")`
*   `dofile_once("data/scripts/biome_scripts.lua")`