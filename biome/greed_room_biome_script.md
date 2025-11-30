---
title: Greed Room Biome Script
category: biome
---

---

# Greed Room Biome Script

This script defines the behavior and content for the "Greed Room" biome in Noita. It handles the loading of the biome's visual scene and the spawning of specific entities.

## Core Functionality

### `init(x, y, w, h)`

This is the primary initialization function for the Greed Room biome.

*   **Purpose:** Loads the visual representation of the Greed Room.
*   **Parameters:**
    *   `x`, `y`: Coordinates for loading the scene.
    *   `w`, `h`: Dimensions of the area (often unused in this context).
*   **Action:** Calls `LoadPixelScene` to load the `greed_room.png` pixel scene at the specified coordinates.

### `spawn_secret(x, y)`

This function is responsible for spawning a specific secret entity within the Greed Room.

*   **Purpose:** Spawns the "Greed Curse" item.
*   **Parameters:**
    *   `x`, `y`: Coordinates where the secret entity will be spawned.
*   **Action:** Calls `EntityLoad` to place `greed_curse.xml` at the given `x`, `y` position.

## Registered Spawn Functions

The following functions are registered to be called at specific points during the game's execution, likely tied to biome generation or specific events.

*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the `init` function to be called. The `0xffffeedd` likely represents a specific biome ID or trigger.
*   `RegisterSpawnFunction( 0xff31d0b4, "spawn_secret" )`: Registers the `spawn_secret` function. The `0xff31d0b4` likely represents another biome ID or trigger.

## Unused/Placeholder Functions

The following functions are defined but appear to be empty or serve as placeholders. They do not contribute to the current functionality of the Greed Room biome script.

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

These functions might be intended for future expansion or were part of a previous iteration of the biome's design.