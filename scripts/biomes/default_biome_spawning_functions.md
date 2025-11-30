---
title: Default Biome Spawning Functions
category: scripts/biomes
---

---

# Default Biome Spawning Functions

This script provides fallback functions for spawning entities in biomes when a specific biome definition isn't found. These are basic spawning routines designed to be called by the game's biome generation system.

## Core Spawning Functions

These functions are intended to be called by the game's biome system to populate areas with entities.

### `spawn_small_enemies(x, y, w, h)`

Spawns a small enemy entity within a given area.

*   **Purpose**: To add basic enemy presence to a biome.
*   **Entity Spawned**: `data/entities/animals/sheep.xml`
*   **Positioning**: The spawn position is slightly randomized within a small offset from the provided `x` and `y` coordinates.

### `spawn_big_enemies(x, y, w, h)`

Spawns a larger, more significant enemy entity within a given area.

*   **Purpose**: To introduce tougher enemies to a biome.
*   **Entity Spawned**: `data/entities/animals/worm_big.xml`
*   **Positioning**: Similar to `spawn_small_enemies`, the spawn position is slightly randomized.

### `spawn_items(x, y, w, h)`

A placeholder function for spawning items. Currently, it does not spawn any items.

*   **Purpose**: Intended for item distribution within biomes.
*   **Current Implementation**: No entities are spawned.

### `spawn_lamp(x, y, w, h)`

A placeholder function for spawning lamps. Currently, it does not spawn any lamps.

*   **Purpose**: Intended for lighting elements in biomes.
*   **Current Implementation**: No entities are spawned.

### `spawn_barrels(x, y, w, h)`

A placeholder function for spawning barrels. Currently, it does not spawn any barrels.

*   **Purpose**: Intended for environmental props like barrels.
*   **Current Implementation**: No entities are spawned.

## Usage Notes

*   These functions are called by the Noita engine when a biome requires entity placement and no specific biome script is available to handle it.
*   The `SetRandomSeed(x, y)` call ensures that the random number generator is seeded based on the location, leading to more consistent spawning patterns for the same coordinates.
*   The `w` and `h` parameters (width and height) are provided but not directly used in the current implementations of these specific functions. They are part of the general biome spawning interface.