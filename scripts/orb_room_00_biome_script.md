---
title: Orb Room 00 Biome Script
category: scripts
---

---

# Orb Room 00 Biome Script

This script defines the behavior and content for a specific type of orb room biome in Noita. It focuses on loading the visual assets and spawning the primary orb entity.

## Key Attributes

*   **`CHEST_LEVEL`**: Indicates the difficulty or tier of chests that might spawn in this biome. Set to `3`.
*   **`RegisterSpawnFunction`**: Registers the `init` function to be called when this biome is spawned. The first argument `0xffffeedd` is likely an internal identifier.

## Core Functions

### `init(x, y, w, h)`

This is the primary initialization function for the orb room biome.

*   **`LoadPixelScene(filepath, material_filepath, x, y, background_filepath, is_background_animated)`**: This function is crucial for defining the visual layout of the biome.
    *   `"data/biome_impl/orbroom.png"`: The main pixel scene file that defines the room's structure and visuals.
    *   `""`: An empty string, indicating no specific material file is used for the main scene.
    *   `x, y`: The coordinates where the scene will be loaded.
    *   `"data/biome_impl/orbroom_background.png"`: The background image for the orb room.
    *   `true`: Specifies that the background image is animated.

### `spawn_orb(x, y)`

This function handles the spawning of the main orb and associated items within the orb room.

*   **`EntityLoad(entity_filepath, x, y)`**: Loads specific entities into the game world.
    *   `"data/entities/items/orbs/orb_00.xml"`: Spawns the primary orb entity.
    *   `"data/entities/items/books/book_00.xml"`: Spawns a book entity near the orb.
    *   `"data/entities/misc/music_energy_000.xml"`: Spawns a music energy entity.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script. They are likely placeholders for potential future additions or are handled by other scripts.

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