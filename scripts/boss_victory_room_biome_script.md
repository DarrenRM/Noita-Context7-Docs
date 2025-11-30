---
title: Boss Victory Room Biome Script
category: scripts
---

# Boss Victory Room Biome Script

This script defines the behavior and content for the "Boss Victory Room" biome in Noita. It handles the loading of visual assets and the spawning of specific entities upon entering the room.

## Core Functions

### `init(x, y, w, h)`
This function is called when the biome is initialized. It's responsible for loading the visual elements of the victory room.

*   **`LoadPixelScene(filepath_png, filepath_visual_png, x, y, filepath_background_png, boolean)`**: Loads the pixel scene data for the biome.
    *   `data/biome_impl/boss_victoryroom.png`: The primary pixel data for the room.
    *   `data/biome_impl/boss_victoryroom_visual.png`: Visual layer for the room.
    *   `x`, `y`: Coordinates for placing the scene.
    *   `data/biome_impl/boss_victoryroom_background.png`: Background image for the room.
    *   `true`: Indicates whether to load the background.

### `spawn_sampo_spot(x, y)`
This function spawns specific entities related to the "Sampo" mechanism and ambient elements within the victory room.

*   **`EntityLoad(filepath_xml, x, y)`**: Loads an entity from an XML file at the specified coordinates.
    *   `data/entities/animals/boss_centipede/ending/ending_sampo_spot_underground.xml`: Spawns the underground Sampo spot.
    *   `data/entities/animals/boss_centipede/boss_victoryroom_mechanism.xml`: Spawns the victory room mechanism.
    *   `data/entities/animals/boss_centipede/boss_victoryroom_ambience.xml`: Spawns ambient effects for the room.

### `spawn_items(x, y)`
This function is intended to spawn items within the victory room.

*   **`spawn_rewards(x, y)`**: Calls a function from `spawn_rewards.lua` to handle item spawning. This likely refers to the rewards obtained after defeating a boss.

## Registered Spawn Functions

These functions are registered to be called at specific points during level generation or biome loading.

*   **`RegisterSpawnFunction(id, function_name)`**: Registers a function to be called with a specific ID.
    *   `0xffffeedd`, `"init"`: Registers the `init` function to be called.
    *   `0xffffd1a1`, `"spawn_sampo_spot"`: Registers the `spawn_sampo_spot` function to be called.

## Unused/Placeholder Functions

The following functions are defined but currently have empty implementations. They are likely placeholders for future development or were part of a more general biome template.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_lamp(x, y)`
*   `spawn_chest(x, y)`
*   `spawn_blood(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_save(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_persistent_teleport(x, y)`
*   `spawn_candles(x, y)`