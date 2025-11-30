---
title: Mountain Biome - Entity Spawning Configuration
category: biome
---

# Mountain Biome - Entity Spawning Configuration

This document details the entity spawning configurations for the Mountain biome in Noita, focusing on the `g_lamp` table and associated spawning functions.

## `g_lamp` Table

This table defines the probability and count of specific entities that can spawn within the Mountain biome.

### Key Attributes:

*   **`total_prob`**: The sum of all `prob` values in the table. Used for normalization or internal calculations.
*   **`prob`**: The relative probability of an entity spawning. Higher values mean a greater chance.
*   **`min_count`**: The minimum number of instances of the entity to spawn.
*   **`max_count`**: The maximum number of instances of the entity to spawn.
*   **`entity`**: The file path to the entity's XML definition.

### Spawnable Entities:

| `prob` | `min_count` | `max_count` | `entity`                                  | Description                               |
| :----- | :---------- | :---------- | :---------------------------------------- | :---------------------------------------- |
| 0.1    | 0           | 0           | `""`                                      | Represents empty space (no spawn).        |
| 1.5    | 1           | 1           | `data/entities/props/physics/lantern_small.xml` | Spawns a small physics lantern.           |

## Spawning Functions

These Lua functions are responsible for loading specific entities into the game world at given coordinates.

### Key Functions:

*   **`spawn_lamp( x, y )`**:
    *   Loads `data/entities/props/physics/lantern_small.xml` at the specified `x` and `y` coordinates.

*   **`spawn_small_enemies( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning smaller enemy types.

*   **`spawn_big_enemies( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning larger enemy types.

*   **`spawn_items( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning various items.

*   **`spawn_props( x, y )`**, **`spawn_props2( x, y )`**, **`spawn_props3( x, y )`**:
    *   Placeholder functions, no implementation provided in the source. Likely intended for spawning different categories of props.

*   **`spawn_chest( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning chests.

*   **`spawn_blood( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning blood effects.

*   **`load_pixel_scene( x, y )`**, **`load_pixel_scene2( x, y )`**:
    *   Placeholder functions, no implementation provided in the source. Likely intended for loading pre-defined pixel art scenes.

*   **`spawn_unique_enemy( x, y )`**, **`spawn_unique_enemy2( x, y )`**, **`spawn_unique_enemy3( x, y )`**:
    *   Placeholder functions, no implementation provided in the source. Likely intended for spawning unique or boss-type enemies.

*   **`spawn_save( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning save points or related mechanics.

*   **`spawn_ghostlamp( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning a "ghost lamp" entity.

*   **`spawn_persistent_teleport( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning persistent teleportation points.

*   **`spawn_candles( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning candles.

*   **`spawn_potions( x, y )`**:
    *   Placeholder function, no implementation provided in the source. Likely intended for spawning potions.