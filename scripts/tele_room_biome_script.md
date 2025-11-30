---
title: Tele Room Biome Script
category: scripts/
---

# Tele Room Biome Script

This script defines the behavior and entity spawning for the "Tele Room" biome in Noita. It's primarily responsible for loading the visual representation of the room and placing various teleportation entities.

## Core Functionality

### `init(x, y, w, h)`

This function is called when the Tele Room biome is initialized.

*   **`LoadPixelScene("data/biome_impl/teleroom.png", "", x, y, "", true)`**: Loads the pixel scene data that defines the visual layout and structure of the tele room.

## Spawn Functions

The script registers several spawn functions that are triggered at specific points or conditions within the biome.

### `spawn_teleX(x, y)` (where X is 1 through 6)

These functions are responsible for spawning different types of teleportation entities within the tele room.

*   **`EntityLoad("data/entities/buildings/teleport_teleroom_X.xml", x, y)`**: Loads a specific teleport entity XML file at the given coordinates. Each `spawn_teleX` function loads a distinct teleport entity, likely offering different destinations or functionalities.

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

## Key Attributes

*   **`CHEST_LEVEL = 3`**: This constant likely influences the type or rarity of chests that might spawn in this biome, though no chest spawning logic is present in this specific script.
*   **`RegisterSpawnFunction`**: Used to associate specific functions with biome initialization and entity spawning events.
*   **`EntityLoad`**: The primary function for instantiating game entities from XML definitions.
*   **`LoadPixelScene`**: Crucial for defining the visual and physical structure of the biome.