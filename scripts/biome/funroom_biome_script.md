---
title: Funroom Biome Script
category: scripts/biome
---

# Funroom Biome Script

This script defines the behavior and content spawning for the "Funroom" biome in Noita. It's a relatively simple biome focused on loading a specific pixel scene and spawning a single unique entity.

## Core Functionality

### `init(x, y, w, h)`

This function is called when the biome is initialized. Its primary purpose is to load the visual representation of the Funroom.

*   **`LoadPixelScene("data/biome_impl/funroom.png", "", x, y, "", true)`**: Loads the pixel scene from the specified PNG file. This file dictates the visual layout and structure of the Funroom.

### `spawn_fun(x, y)`

This function is responsible for spawning specific entities within the Funroom.

*   **`EntityLoad("data/entities/buildings/funroom_check.xml", x, y)`**: Loads the `funroom_check.xml` entity. This is the main entity associated with the Funroom, likely containing its unique properties or interactions.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation. They are likely placeholders or remnants from a more complex biome structure.

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

*   **`CHEST_LEVEL = 3`**: This constant is defined but not used within the provided script. It might be intended for a more general chest spawning system or a feature not implemented in this specific biome.

## Registration

*   **`RegisterSpawnFunction(0xffffeedd, "init")`**: Registers the `init` function to be called with a specific identifier.
*   **`RegisterSpawnFunction(0xff00ffaa, "spawn_fun")`**: Registers the `spawn_fun` function to be called with another specific identifier. These identifiers are likely used by the game's director system to trigger biome-specific events.