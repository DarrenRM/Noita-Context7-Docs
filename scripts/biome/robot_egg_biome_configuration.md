---
title: Robot Egg Biome Configuration
category: scripts/biome
---

# Robot Egg Biome Configuration

This document details the configuration for the "Robot Egg" biome in Noita, focusing on enemy spawns, item drops, and environmental elements.

## Core Biome Functions

The `robot_egg.lua` script registers several functions that are called by the game's director system to populate the biome.

### Registered Spawn Functions

| Color ID | Function Name   | Description                                     |
| :------- | :-------------- | :---------------------------------------------- |
| `0xffffeedd` | `init`          | Initializes the biome's visual and background.  |
| `0xff548f77` | `spawn_teleport` | Spawns a teleport entity.                       |
| `0xff709615` | `spawn_chest`   | Spawns a chest entity.                          |

## Enemy Spawns

This section defines the types and probabilities of enemies that can spawn within the Robot Egg biome.

### `g_small_enemies`

A table defining the smaller enemy entities that can appear.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `prob`      | `0.2`                               | Probability of spawning this entity.      |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/animals/vault/roboguard.xml` | Path to the Roboguard entity XML.         |
| `entity`    | `data/entities/animals/vault/assassin.xml`  | Path to the Assassin entity XML.          |
| `entity`    | `data/entities/animals/monk.xml`            | Path to the Monk entity XML.              |

### `g_big_enemies`

A table defining larger enemy entities.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `prob`      | `1.0`                               | Probability of spawning this entity.      |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `data/entities/animals/spearbot.xml`        | Path to the Spearbot entity XML.          |

## Item Spawns

This section outlines the items that can be found within the biome.

### `g_lamp`

Defines the probability and type of lamps that can spawn.

| Attribute   | Value                                       | Description                               |
| :---------- | :------------------------------------------ | :---------------------------------------- |
| `prob`      | `0.8`                                       | Probability of spawning a lantern.        |
| `min_count` | `1`                                         | Minimum number of lanterns to spawn.      |
| `max_count` | `1`                                         | Maximum number of lanterns to spawn.      |
| `entity`    | `data/entities/props/physics/lantern_small.xml` | Path to the small lantern entity XML.     |

### `g_items`

Defines the wands and other items that can be found.

| Attribute   | Value                                     | Description                                   |
| :---------- | :---------------------------------------- | :-------------------------------------------- |
| `prob`      | `5`                                       | Probability weight for spawning this item.    |
| `min_count` | `1`                                       | Minimum number of items to spawn.             |
| `max_count` | `1`                                       | Maximum number of items to spawn.             |
| `entity`    | `data/entities/items/wand_level_05.xml`     | Path to a level 5 wand entity XML.            |
| `entity`    | `data/entities/items/wand_level_05_better.xml` | Path to a better level 5 wand entity XML.     |
| `entity`    | `data/entities/items/wand_unshuffle_03.xml` | Path to an unshuffle wand (level 3) entity XML. |
| `entity`    | `data/entities/items/wand_unshuffle_04.xml` | Path to an unshuffle wand (level 4) entity XML. |

## Environmental Elements

This section covers other entities and props that contribute to the biome's atmosphere and gameplay.

### `g_ghostlamp`

Defines the ghostly lamp entity.

| Attribute   | Value                                           | Description                                     |
| :---------- | :---------------------------------------------- | :---------------------------------------------- |
| `prob`      | `1.0`                                           | Probability of spawning this entity.            |
| `min_count` | `1`                                             | Minimum number of entities to spawn.            |
| `max_count` | `1`                                             | Maximum number of entities to spawn.            |
| `entity`    | `data/entities/props/physics/chain_torch_ghostly.xml` | Path to the ghostly chain torch entity XML.     |

### `g_candles`

Defines the different types of candles that can spawn.

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `prob`      | `0.33`                                | Probability of spawning this candle type. |
| `min_count` | `1`                                   | Minimum number of candles to spawn.       |
| `max_count` | `1`                                   | Maximum number of candles to spawn.       |
| `entity`    | `data/entities/props/physics_candle_1.xml` | Path to candle type 1 entity XML.         |
| `entity`    | `data/entities/props/physics_candle_2.xml` | Path to candle type 2 entity XML.         |
| `entity`    | `data/entities/props/physics_candle_3.xml` | Path to candle type 3 entity XML.         |

## Biome Initialization and Spawning Functions

These are the primary functions called by the game engine to load and populate the biome.

### `init(x, y, w, h)`

Loads the visual and background assets for the Robot Egg biome.

```lua
function init(x, y, w, h)
	LoadPixelScene( "data/biome_impl/robot_egg.png", "data/biome_impl/robot_egg_visual.png", x, y, "data/biome_impl/robot_egg_background.png", true )
end
```

### `spawn_small_enemies(x, y)`

Spawns entities defined in `g_small_enemies`.

```lua
function spawn_small_enemies(x, y)
	spawn(g_small_enemies,x,y)
end
```

### `spawn_big_enemies(x, y)`

Spawns entities defined in `g_big_enemies`.

```lua
function spawn_big_enemies(x, y)
	spawn(g_big_enemies,x,y)
end
```

### `spawn_items(x, y)`

Spawns items defined in `g_items`.

```lua
function spawn_items(x, y)
	spawn(g_items,x,y)
end
```

### `spawn_lamp(x, y)`

Spawns entities defined in `g_lamp`.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x,y+6,0,0)
end
```

### `spawn_teleport(x, y)`

Loads a specific teleport entity.

```lua
function spawn_teleport(x, y)
	EntityLoad("data/entities/buildings/teleport_robot_egg_return.xml", x, y)
end
```

### `spawn_chest(x, y)`

Loads a specific steel chest entity.

```lua
function spawn_chest(x, y)
	EntityLoad("data/entities/buildings/chest_steel.xml", x, y)
end
```