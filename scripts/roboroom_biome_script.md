---
title: Roboroom Biome Script
category: scripts
---

# Roboroom Biome Script

This script defines the behavior and spawning logic for the "Roboroom" biome in Noita. It handles the loading of the biome's visual representation and the spawning of specific entities within it.

## Core Functionality

### `init(x, y, w, h)`

This function is called when the Roboroom biome is initialized. It's responsible for loading the visual assets of the biome.

*   **`LoadPixelScene( "data/biome_impl/roboroom.png", "", x, y, "", true )`**: Loads the pixel scene data for the Roboroom, defining its layout and visual appearance.

### `spawn_essence(x, y)`

This function is called to spawn specific "essence" entities within the Roboroom.

*   **`EntityLoad( "data/entities/animals/boss_robot/boss_robot.xml", x, y )`**: Spawns the `boss_robot.xml` entity at the given coordinates. This is the primary unique entity associated with this biome.

## Registered Spawn Functions

The following functions are registered to be called at specific points during the game's progression or biome generation.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called. The `0xffffeedd` likely represents a specific biome ID or event trigger.
*   **`RegisterSpawnFunction( 0xff31d0b4, "spawn_essence" )`**: Registers the `spawn_essence` function to be called. The `0xff31d0b4` likely represents another biome ID or event trigger, specifically for spawning the boss robot.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders for future development or were part of a more generalized biome script template.

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