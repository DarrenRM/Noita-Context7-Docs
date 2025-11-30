---
title: Essenceroom Alc Biome Script
category: scripts
---

# Essenceroom Alc Biome Script

This script defines the behavior and content for the "Essenceroom Alc" biome in Noita. It focuses on loading specific visual assets and spawning a particular type of item.

## Core Functionality

### `init(x, y, w, h)`

This function is called when the biome is initialized. It's responsible for loading the visual elements of the biome.

*   **`LoadPixelScene(...)`**: This is the primary function used to load the visual components of the biome.
    *   `"data/biome_impl/essenceroom_submerged.png"`: The main pixel scene for the submerged aspect of the room.
    *   `"data/biome_impl/essenceroom_visual.png"`: The visual layer of the room.
    *   `x, y`: The coordinates where the scene is loaded.
    *   `"data/biome_impl/essenceroom_background_with_diamond.png"`: The background image, featuring a diamond element.
    *   `true`: A boolean flag, likely indicating whether to use parallax or other advanced rendering.

### `spawn_essence(x, y)`

This function is triggered to spawn a specific item within the biome.

*   **`EntityLoad("data/entities/items/pickup/essence_alcohol.xml", x, y)`**: This line loads an entity from an XML file.
    *   `"data/entities/items/pickup/essence_alcohol.xml"`: Specifies the entity to be loaded, which is an "essence alcohol" pickup item.
    *   `x, y`: The coordinates where the item will be spawned.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation, indicating they are placeholders or were intended for future use.

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

## Registration

### `RegisterSpawnFunction(...)`

These calls register specific Lua functions to be executed at certain points during the game's execution, likely tied to biome generation or entity spawning events.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called with a specific identifier (`0xffffeedd`).
*   **`RegisterSpawnFunction( 0xff31d0b4, "spawn_essence" )`**: Registers the `spawn_essence` function to be called with a different identifier (`0xff31d0b4`).