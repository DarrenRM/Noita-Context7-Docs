---
title: Magic Gate Biome Configuration
category: scripts/biome
---

# Magic Gate Biome Configuration

This file defines the spawning rules and visual elements for the "Magic Gate" biome in Noita. It specifies which entities, items, and visual scenes can appear within this biome.

## Core Biome Initialization

The `init` function is responsible for loading the primary visual assets of the Magic Gate biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/magic_gate.png", "", x, y, "", true )
end
```

-   **`LoadPixelScene`**: This function loads the visual representation of the biome.
    -   `"data/biome_impl/magic_gate.png"`: The primary texture file for the biome.
    -   `""`: No specific background file is used.
    -   `x, y`: The coordinates where the biome is placed.
    -   `""`: No additional parameters.
    -   `true`: Indicates that this is a primary scene load.

## Entity Spawning Tables

These tables define the probabilities and types of entities that can spawn within the biome.

### `g_small_enemies`

Defines the probability and count for smaller enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file. An empty string means no entity spawns. |

| prob  | min_count | max_count | entity                               |
| :---- | :-------- | :-------- | :----------------------------------- |
| 0.4   | 0         | 0         | ""                                   |
| 0.1   | 1         | 1         | "data/entities/animals/gazer.xml"    |
| 0.1   | 1         | 1         | "data/entities/animals/bloodcrystal_physics.xml" |

### `g_big_enemies`

Defines the probability and count for larger enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file. An empty string means no entity spawns. |

| prob  | min_count | max_count | entity |
| :---- | :-------- | :-------- | :----- |
| 0.4   | 0         | 0         | ""     |

### `g_props`

Defines the probability and count for various props.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `offset_y`  | Vertical offset for spawning.                                            |
| `entity`    | Path to the entity's XML file.                                           |

| prob  | min_count | max_count | offset_y | entity                           |
| :---- | :-------- | :-------- | :------- | :------------------------------- |
| 0.5   | 1         | 1         | -4       | "data/entities/buildings/spike.xml" |

### `g_unique_enemy`

Defines the probability and count for unique enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `offset_x`  | Horizontal offset for spawning.                                          |
| `entity`    | Path to the entity's XML file. An empty string means no entity spawns. |

| prob  | min_count | max_count | offset_x | entity                                 |
| :---- | :-------- | :-------- | :------- | :------------------------------------- |
| 0.1   | 0         | 0         | 0        | ""                                     |
| 1.0   | 1         | 1         | 2        | "data/entities/buildings/arrowtrap_right.xml" |

### `g_large_enemies`

Defines the probability and count for large enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `offset_x`  | Horizontal offset for spawning.                                          |
| `entity`    | Path to the entity's XML file. An empty string means no entity spawns. |

| prob  | min_count | max_count | offset_x | entity                                |
| :---- | :-------- | :-------- | :------- | :------------------------------------ |
| 0.1   | 0         | 0         | 0        | ""                                    |
| 1.0   | 1         | 1         | 1        | "data/entities/buildings/arrowtrap_left.xml" |

## Item Spawning Tables

These tables define the probabilities and types of items that can spawn within the biome.

### `g_items`

Defines the probability and count for general item drops.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity's XML file. An empty string means no entity spawns. |

| prob | min_count | max_count | entity                       |
| :--- | :-------- | :-------- | :--------------------------- |
| 0    | 0         | 0         | ""                           |
| 5    | 1         | 1         | "data/entities/items/wand_level_04.xml" |

## Visual Scene Tables

These tables define specific visual elements or scenes that can be loaded.

### `g_pixel_scene_01`

Defines specific material files for pixel scenes.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `prob`          | Probability of this entry being selected.                                |
| `material_file` | Path to the material texture file.                                       |
| `visual_file`   | Path to the visual effect file (if any).                                 |
| `background_file` | Path to the background file (if any).                                    |
| `is_unique`     | Flag indicating if this scene is unique (0 for not unique).              |

| prob | material_file                               | visual_file | background_file | is_unique |
| :--- | :------------------------------------------ | :---------- | :-------------- | :-------- |
| 1.0  | "data/biome_impl/crypt/cathedral.png"       | ""          | ""              | 0         |
| 1.0  | "data/biome_impl/crypt/mining.png"          | ""          | ""              | 0         |

### `g_pixel_scene_02`

Another table for defining pixel scene elements.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `prob`          | Probability of this entry being selected.                                |
| `material_file` | Path to the material texture file.                                       |
| `visual_file`   | Path to the visual effect file (if any).                                 |
| `background_file` | Path to the background file (if any).                                    |
| `is_unique`     | Flag indicating if this scene is unique (0 for not unique).              |

| prob | material_file | visual_file | background_file | is_unique |
| :--- | :------------ | :---------- | :-------------- | :-------- |
| 0.5  | ""            | ""          | ""              | 0         |

## Specific Entity Spawning Functions

These functions are called by the game's director to spawn specific entities or load scenes at given coordinates.

### `spawn_small_enemies(x, y)`

Spawns entities defined in `g_small_enemies`.

### `spawn_big_enemies(x, y)`

Spawns entities defined in `g_big_enemies`.

### `spawn_items(x, y)`

Spawns items, with a chance to load a specific wand altar scene.

```lua
function spawn_items(x, y)
	local r = ProceduralRandom( x-11.631, y+10.2257 )

	if (r > 0.38) then
		LoadPixelScene( "data/biome_impl/wand_altar.png", "data/biome_impl/wand_altar_visual.png", x-10, y-17, "", true )
	end
end
```

### `load_pixel_scene2(x, y)`

Loads a random pixel scene from `g_pixel_scene_02`.

### `spawn_lamp(x, y)`

Spawns a lamp prop.

### `spawn_props(x, y)`

Spawns props defined in `g_props`.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies defined in `g_unique_enemy`.

### `spawn_large_enemies(x, y)`

Spawns large enemies defined in `g_large_enemies`.

### `load_pixel_scene(x, y)`

Loads a random pixel scene from `g_pixel_scene_01`.

## Unused/Placeholder Functions

These functions are defined but do not contain any implementation in this file, meaning they have no effect.

-   `spawn_apparition(x, y)`
-   `spawn_candles(x, y)`
-   `spawn_ghostlamp(x, y)`
-   `spawn_potions(x, y)`