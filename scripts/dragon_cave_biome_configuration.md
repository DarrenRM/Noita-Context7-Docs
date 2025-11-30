---
title: Dragon Cave Biome Configuration
category: scripts
---

# Dragon Cave Biome Configuration

This document details the configuration for the Dragon Cave biome in Noita, focusing on entity spawning and visual elements.

## Core Biome Setup

The `dragoncave.lua` script defines the core elements and spawning logic for the Dragon Cave biome.

### Initialization

The `init` function is responsible for loading the primary visual assets of the biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/dragoncave.png", "data/biome_impl/dragoncave_visual.png", x, y, "data/biome_impl/dragoncave_background.png", true )
end
```

*   **`x`, `y`, `w`, `h`**: Coordinates and dimensions for loading the biome.
*   **`data/biome_impl/dragoncave.png`**: The primary material layer for the biome.
*   **`data/biome_impl/dragoncave_visual.png`**: Visual overlay for the biome.
*   **`data/biome_impl/dragoncave_background.png`**: The background layer for the biome.
*   **`true`**: Indicates that this is a primary biome load.

### Spawn Functions

Various functions are registered to handle the spawning of different entities and elements within the biome.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function for a specific color code.
*   **`RegisterSpawnFunction( 0xffC8C800, "spawn_lamp2" )`**: Registers `spawn_lamp2`.
*   **`RegisterSpawnFunction( 0xff00AC64, "load_pixel_scene4" )`**: Registers `load_pixel_scene4`.
*   **`RegisterSpawnFunction( 0xff80FF5A, "spawn_vines" )`**: Registers `spawn_vines`.
*   **`RegisterSpawnFunction( 0xff943030, "spawn_dragonspot" )`**: Registers `spawn_dragonspot`.

## Entity Spawning Tables

These tables define the probabilities and types of entities that can spawn within the Dragon Cave biome.

### `g_small_enemies`

Defines the pool of smaller enemies that can appear.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.5`                                         |
| `min_count` | Minimum number of entities to spawn.            | `0`                                           |
| `max_count` | Maximum number of entities to spawn.            | `4`                                           |
| `entity`    | Path to the entity XML file.                    | `"data/entities/animals/fly.xml"`             |
| `entities`  | List of entities for combined spawns (rare).    | `{"entity1.xml", "entity2.xml"}`              |

**Key Entries:**

*   **Fly:** `prob = 0.5`, `min_count = 2`, `max_count = 4`, `entity = "data/entities/animals/fly.xml"`
*   **Lukki (Long Leg):** `prob = 0.09`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/animals/lukki/lukki_longleg.xml"`
*   **Shooter Flower:** `prob = 0.1`, `min_count = 1`, `max_count = 2`, `entity = "data/entities/animals/shooterflower.xml"`
*   **Mine:** `prob = 0.2`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/items/mine.xml"`

### `g_big_enemies`

Defines the pool of larger enemies that can appear.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.6`                                         |
| `min_count` | Minimum number of entities to spawn.            | `0`                                           |
| `max_count` | Maximum number of entities to spawn.            | `3`                                           |
| `entity`    | Path to the entity XML file.                    | `"data/entities/animals/fungus.xml"`          |
| `entities`  | List of entities for combined spawns.           | `{"entity1.xml", "entity2.xml"}`              |

**Key Entries:**

*   **Fungus:** `prob = 0.1`, `min_count = 2`, `max_count = 3`, `entity = "data/entities/animals/fungus.xml"`
*   **Bloom:** `prob = 0.1`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/animals/bloom.xml"`
*   **Scavenger (Poison/Clusterbomb):** `prob = 0.05`, `min_count = 1`, `max_count = 1`, `entities = {...}`

### `g_unique_enemy`

Defines unique or special enemy spawns.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `1.0`                                         |
| `min_count` | Minimum number of entities to spawn.            | `0`                                           |
| `max_count` | Maximum number of entities to spawn.            | `1`                                           |
| `entity`    | Path to the entity XML file.                    | `"data/entities/buildings/physics_cocoon.xml"`|

**Key Entries:**

*   **Physics Cocoon:** `prob = 1.0`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/buildings/physics_cocoon.xml"`

### `g_items`

Defines the types of items that can spawn.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `5`                                           |
| `min_count` | Minimum number of items to spawn.               | `1`                                           |
| `max_count` | Maximum number of items to spawn.               | `1`                                           |
| `entity`    | Path to the item XML file.                      | `"data/entities/items/wand_level_04.xml"`     |

**Key Entries:**

*   **Wand (Level 04):** `prob = 5`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/items/wand_level_04.xml"`
*   **Wand (Unshuffle 02):** `prob = 3`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/items/wand_unshuffle_02.xml"`

### `g_nest`

Defines the types of nests that can spawn.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.5`                                         |
| `min_count` | Minimum number of nests to spawn.               | `1`                                           |
| `max_count` | Maximum number of nests to spawn.               | `1`                                           |
| `entity`    | Path to the nest entity XML file.               | `"data/entities/buildings/flynest.xml"`       |

### `g_props`

Defines the types of environmental props that can spawn.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.5`                                         |
| `min_count` | Minimum number of props to spawn.               | `0`                                           |
| `max_count` | Maximum number of props to spawn.               | `1`                                           |
| `entity`    | Path to the prop entity XML file.               | `"data/entities/props/physics_barrel_radioactive.xml"` |
| `offset_y`  | Vertical offset for spawning.                   | `-8`                                          |

**Key Entries:**

*   **Radioactive Barrel:** `prob = 0.5`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/props/physics_barrel_radioactive.xml"`
*   **Explosive Box:** `prob = 0.5`, `min_count = 1`, `max_count = 1`, `entity = "data/entities/props/physics_box_explosive.xml"`

### `g_lamp` and `g_lamp2`

These tables define different types of lamps that can spawn.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.6`                                         |
| `min_count` | Minimum number of lamps to spawn.               | `1`                                           |
| `max_count` | Maximum number of lamps to spawn.               | `1`                                           |
| `entity`    | Path to the lamp entity XML file.               | `"data/entities/props/physics_torch_stand.xml"` |

### `g_pixel_scene_01`, `g_pixel_scene_02`, `g_pixel_scene_04`

These tables define various pre-designed pixel scenes that can be loaded into the biome.

| Attribute        | Description                                     | Example                                       |
| :--------------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`           | Probability of this scene being chosen.         | `0.5`                                         |
| `material_file`  | Path to the material PNG file.                  | `"data/biome_impl/rainforest/pit01.png"`      |
| `visual_file`    | Path to the visual PNG file (optional).         | `""`                                          |
| `background_file`| Path to the background PNG file (optional).     | `"data/biome_impl/rainforest/hut01_background.png"` |
| `is_unique`      | Whether this scene is unique (0 or 1).          | `0`                                           |

### `g_ghostlamp`

Defines the spawning of ghostly chain torches.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `1.0`                                         |
| `min_count` | Minimum number of lamps to spawn.               | `1`                                           |
| `max_count` | Maximum number of lamps to spawn.               | `1`                                           |
| `offset_y`  | Vertical offset for spawning.                   | `10`                                          |
| `entity`    | Path to the entity XML file.                    | `"data/entities/props/physics_chain_torch_ghostly.xml"` |

### `g_candles`

Defines the spawning of different types of candles.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.33`                                        |
| `min_count` | Minimum number of candles to spawn.             | `1`                                           |
| `max_count` | Maximum number of candles to spawn.             | `1`                                           |
| `entity`    | Path to the candle entity XML file.             | `"data/entities/props/physics_candle_1.xml"`  |

### `g_vines`

Defines the spawning of various vine types.

| Attribute   | Description                                     | Example                                       |
| :---------- | :---------------------------------------------- | :-------------------------------------------- |
| `prob`      | Probability of this entry being chosen.         | `0.4`                                         |
| `min_count` | Minimum number of vines to spawn.               | `1`                                           |
| `max_count` | Maximum number of vines to spawn.               | `1`                                           |
| `entity`    | Path to the vine entity XML file.               | `"data/entities/verlet_chains/vines/verlet_vine.xml"` |

## Helper Functions

These functions are used internally by the biome script for spawning.

*   **`spawn_small_enemies(x, y)`**: Spawns small enemies using `spawn_hp_mult`.
*   **`spawn_big_enemies(x, y)`**: Spawns big enemies using `spawn_hp_mult`.
*   **`spawn_unique_enemy(x, y)`**: Spawns unique enemies using `spawn_hp_mult`.
*   **`spawn_items(x, y)`**: Spawns items, including a chance to load a wand altar.
*   **`spawn_nest(x, y)`**: Spawns nests using the `g_nest` table.
*   **`spawn_props(x, y)`**: Spawns props using the `g_props` table.
*   **`spawn_lamp(x, y)`**: Spawns lamps using the `g_lamp` table.
*   **`spawn_lamp2(x, y)`**: Spawns lamps using the `g_lamp2` table.
*   **`load_pixel_scene(x, y)`**: Loads a random pixel scene from `g_pixel_scene_01`.
*   **`load_pixel_scene2(x, y)`**: Loads a random pixel scene from `g_pixel_scene_02`.
*   **`load_pixel_scene4(x, y)`**: Loads a random pixel scene from `g_pixel_scene_04`.
*   **`spawn_vines(x, y)`**: Spawns vines using the `g_vines` table.
*   **`spawn_dragonspot(x, y)`**: Spawns a dragonspot entity.