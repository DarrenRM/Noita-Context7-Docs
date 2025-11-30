---
title: Boss Limbs Arena Biome Script
category: scripts/biome
---

# Boss Limbs Arena Biome Script

This script defines the behavior and entity spawning for the "Boss Limbs Arena" biome in Noita. It's a relatively simple biome script focused on loading a specific pixel scene and spawning a boss entity.

## Core Functions

### `init(x, y, w, h)`
This function is called when the biome is initialized. It's responsible for loading the visual representation of the arena.

*   **`LoadPixelScene( "data/biome_impl/boss_limbs_arena.png", "", x, y, "", true )`**: Loads the pixel scene data for the boss limbs arena. This defines the physical layout and visual appearance of the area.

### `spawn_boss_limbs(x, y)`
This function handles the spawning of the boss entity within the arena.

*   **`local maptilex = math.floor(x / 512)`**: Calculates the map tile X-coordinate. This is used to ensure the boss is spawned only once.
*   **`if (maptilex == 1) then ... end`**: Checks if the current tile is the designated spawn tile for the boss.
*   **`EntityLoad( "data/entities/animals/boss_limbs/boss_limbs.xml", x, y )`**: If the condition is met, this line loads the `boss_limbs.xml` entity, which represents the boss creature, at the specified coordinates.

## Registered Spawn Functions

These functions are registered with the game's director system to be called at specific times or under certain conditions.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called with a specific internal identifier.
*   **`RegisterSpawnFunction( 0xffa37c62, "spawn_boss_limbs" )`**: Registers the `spawn_boss_limbs` function to be called with another internal identifier.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders or remnants from a more complex biome template.

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