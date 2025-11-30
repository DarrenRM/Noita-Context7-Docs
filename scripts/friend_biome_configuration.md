---
title: Friend Biome Configuration
category: scripts/
---

# Friend Biome Configuration

This script defines the configuration for a specific biome in Noita, referred to as the "Friend Biome". It handles the loading of biome visuals and the spawning of various entities within this area.

## Core Biome Logic

### `init(x, y, w, h)`

This function is the primary entry point for initializing the biome. It sets the random seed and determines which visual scene to load based on a random chance.

*   **`SetRandomSeed(24, 32)`**: Initializes the random number generator for consistent biome generation.
*   **Visual Scene Loading**:
    *   With a 1 in 6 chance, it loads `data/biome_impl/cavern.png` and `data/biome_impl/cavern_background.png`.
    *   Otherwise, it loads `data/biome_impl/friendroom.png` as the primary visual.

## Entity Spawning Functions

The script registers several functions to spawn specific entities at different points within the biome.

### Registered Spawn Functions

These functions are called by the game's director system based on specific biome IDs.

*   **`init`**: Called for general biome initialization.
*   **`spawn_fruit`**: Spawns `gourd.xml`.
*   **`spawn_killer`**: Spawns `ultimate_killer.xml`.
*   **`spawn_friend`**: Spawns `friend.xml`.
*   **`spawn_tree`**: Spawns trees from the `g_trees` table.
*   **`spawn_vines`**: Spawns vines from the `g_vines` table.

### Individual Spawn Functions

These are placeholder functions that are not implemented in this script but are registered for potential future use or by other scripts.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `spawn_lamp`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_wands`
*   `spawn_orb`

## Entity Configuration Tables

These tables define the entities that can be spawned and their associated probabilities and counts.

### `g_trees`

This table defines the types of trees that can spawn in the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this tree type spawning.                                  |
| `min_count` | Minimum number of this entity to spawn.                                  |
| `max_count` | Maximum number of this entity to spawn.                                  |
| `entity`    | Path to the entity XML file to spawn.                                    |
| `offset_x`  | Optional X-axis offset for entity placement.                             |
| `offset_y`  | Optional Y-axis offset for entity placement.                             |

**Summary**: The `g_trees` table lists several `rainforest_tree` variants with a base probability of 0.4 each. The first entry with an empty `entity` likely serves as a default or placeholder.

### `g_vines`

This table defines the types of vines that can spawn in the biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this vine type spawning.                                  |
| `min_count` | Minimum number of this entity to spawn.                                  |
| `max_count` | Maximum number of this entity to spawn.                                  |
| `entity`    | Path to the entity XML file to spawn.                                    |

**Summary**: This table includes various `verlet_vine` types (short, long, shorter) and `hanging_root_random` with different probabilities. The first entry with an empty `entity` is a placeholder.

### `g_lamp`

This table defines the types of lamps that can spawn.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this lamp type spawning.                                  |
| `min_count` | Minimum number of this entity to spawn.                                  |
| `max_count` | Maximum number of this entity to spawn.                                  |
| `entity`    | Path to the entity XML file to spawn.                                    |

**Summary**: Currently, this table only contains `lantern_small.xml` with a probability of 1.0.

## Specific Spawn Implementations

### `spawn_fruit(x, y)`

Loads the `gourd.xml` entity at the specified coordinates.

```lua
function spawn_fruit( x, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x, y )
end
```

### `spawn_killer(x, y)`

Loads the `ultimate_killer.xml` entity at the specified coordinates.

```lua
function spawn_killer( x, y )
	EntityLoad( "data/entities/animals/ultimate_killer.xml", x, y )
end
```

### `spawn_friend(x, y)`

Loads the `friend.xml` entity at the specified coordinates.

```lua
function spawn_friend( x, y )
	EntityLoad( "data/entities/animals/friend.xml", x, y )
end
```

### `spawn_lamp(x, y)`

Uses the `spawn` utility function to place entities defined in `g_lamp` at the given coordinates.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x,y,0,0)
end
```

### `spawn_tree(x, y)`

Uses the `spawn` utility function to place entities defined in `g_trees` at the given coordinates.

```lua
function spawn_tree(x, y)
	spawn(g_trees,x,y,0,0)
end
```

### `spawn_vines(x, y)`

Uses the `spawn` utility function to place entities defined in `g_vines` at the given coordinates. It also includes a chance for an additional vine spawn.

```lua
function spawn_vines(x, y)
	spawn(g_vines,x+5,y+5)
	-- chance for an extra spawn for denser vineage
	if ProceduralRandomf(x, y) < 0.5 then
		spawn(g_vines,x,y+5)
	end
end
```