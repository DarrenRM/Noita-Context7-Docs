---
title: Friend Biome Script
category: scripts/
---

# Friend Biome Script

This script defines the behavior and content of a specific biome in Noita, referred to as the "Friend Biome". It handles the loading of visual assets and the spawning of various entities within this biome.

## Core Functionality

The script registers several spawn functions that are called by the game's director system at specific points during level generation.

### Registered Spawn Functions

| Event ID | Function Name   | Description                               |
| :------- | :-------------- | :---------------------------------------- |
| `0xffffeedd` | `init`          | Initializes the biome, loads visuals.     |
| `0xff31d0b0` | `spawn_fruit`   | Spawns fruit entities.                    |
| `0xff9dd0b0` | `spawn_killer`  | Spawns "ultimate killer" entities.        |
| `0xff9dd0c0` | `spawn_friend`  | Spawns "friend" entities.                 |
| `0xff9dd0d0` | `spawn_tree`    | Spawns tree entities.                     |
| `0xff80FF5A` | `spawn_vines`   | Spawns vine entities.                     |

## Initialization (`init`)

The `init` function is responsible for setting up the visual appearance of the biome.

-   **Random Seed:** A random seed is set to ensure variation in biome generation.
-   **Visual Loading:**
    -   With a 1 in 6 chance, it loads `data/biome_impl/cavern.png` and `data/biome_impl/cavern_background.png`.
    -   Otherwise, it loads `data/biome_impl/friendroom.png` as the primary visual.

## Entity Spawning Functions

These functions are called by the game to populate the biome with specific entities.

### `spawn_fruit`

Spawns a `gourd.xml` entity, likely a collectible item.

```lua
function spawn_fruit( x, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x, y )
end
```

### `spawn_killer`

Spawns an `ultimate_killer.xml` entity, a type of aggressive animal.

```lua
function spawn_killer( x, y )
	EntityLoad( "data/entities/animals/ultimate_killer.xml", x, y )
end
```

### `spawn_friend`

Spawns a `friend.xml` entity, which is likely a non-hostile or neutral creature.

```lua
function spawn_friend( x, y )
	EntityLoad( "data/entities/animals/friend.xml", x, y )
end
```

### `spawn_tree`

Spawns various types of trees based on probabilities defined in the `g_trees` table.

```lua
function spawn_tree(x, y)
	spawn(g_trees,x,y,0,0)
end
```

### `spawn_vines`

Spawns vine entities, with a chance for additional spawns to create denser vine growth.

```lua
function spawn_vines( x, y )
	spawn(g_vines,x+5,y+5)
	-- chance for an extra spawn for denser vineage
	if ProceduralRandomf(x, y) < 0.5 then
		spawn(g_vines,x,y+5)
	end
end
```

## Entity Configuration Tables

These tables define the entities that can be spawned, their probabilities, and other parameters.

### `g_trees` Table

Defines the types of trees that can spawn in the biome.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `prob`      | Probability of this tree type spawning.         |
| `min_count` | Minimum number of this entity to spawn.         |
| `max_count` | Maximum number of this entity to spawn.         |
| `offset_x`  | Horizontal offset for spawning (if applicable). |
| `offset_y`  | Vertical offset for spawning (if applicable).   |
| `entity`    | Path to the entity's XML file.                  |

**Key Entities:**

-   `data/entities/props/rainforest_tree_01.xml`
-   `data/entities/props/rainforest_tree_02.xml`
-   `data/entities/props/rainforest_tree_03.xml`
-   `data/entities/props/rainforest_tree_04.xml`
-   `data/entities/props/rainforest_tree_05.xml`
-   `data/entities/props/rainforest_tree_06.xml`

### `g_vines` Table

Defines the types of vines that can spawn.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `prob`      | Probability of this vine type spawning.         |
| `min_count` | Minimum number of this entity to spawn.         |
| `max_count` | Maximum number of this entity to spawn.         |
| `entity`    | Path to the entity's XML file.                  |

**Key Entities:**

-   `data/entities/verlet_chains/vines/verlet_vine.xml`
-   `data/entities/verlet_chains/vines/verlet_vine_long.xml`
-   `data/entities/verlet_chains/vines/verlet_vine_short.xml`
-   `data/entities/verlet_chains/vines/verlet_vine_shorter.xml`
-   `data/entities/verlet_chains/root/hanging_root_random.xml`

### `g_lamp` Table

Defines the types of lamps that can spawn.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `prob`      | Probability of this lamp type spawning.         |
| `min_count` | Minimum number of this entity to spawn.         |
| `max_count` | Maximum number of this entity to spawn.         |
| `entity`    | Path to the entity's XML file.                  |

**Key Entity:**

-   `data/entities/props/physics/lantern_small.xml`

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, meaning they have no effect.

-   `spawn_small_enemies`
-   `spawn_big_enemies`
-   `spawn_items`
-   `spawn_props`
-   `spawn_props2`
-   `spawn_props3`
-   `load_pixel_scene`
-   `load_pixel_scene2`
-   `spawn_unique_enemy`
-   `spawn_unique_enemy2`
-   `spawn_unique_enemy3`
-   `spawn_ghostlamp`
-   `spawn_candles`
-   `spawn_potions`
-   `spawn_wands`
-   `spawn_orb`