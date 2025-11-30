---
title: Suspended Container Physics Objects
category: scripts
---

# Suspended Container Physics Objects

This script is responsible for spawning a random assortment of physics objects (stones and props) in a suspended, vertical arrangement. It's designed to create dynamic environmental elements that can interact with the player and other game objects.

## Core Functionality

The script dynamically loads and places various physics-enabled entities. The selection of entities and their vertical positioning is randomized based on the initial position of the container.

## Key Attributes and Elements

### Entity Spawning Logic

The script iterates a random number of times (between 2 and 7) to spawn entities. In each iteration:

*   A random number `r` is generated.
*   If `r` is greater than 0.9, a random prop from the `props` list is chosen.
*   Otherwise, a random stone from the `stones` list is chosen.
*   The selected entity is loaded at a calculated horizontal position (`pos_x + r * 8`) and the current vertical position (`pos_y`).
*   The vertical position (`pos_y`) is then decremented by 5 for the next entity, creating a stacked effect.

### Entity Lists

The script defines two primary lists of entities to be spawned:

#### `stones`

This table contains paths to various stone-based physics objects.

| Index | Entity Path                               |
| :---- | :---------------------------------------- |
| 1     | `data/entities/props/physics_stone_01.xml` |
| 2     | `data/entities/props/physics_stone_02.xml` |
| 3     | `data/entities/props/physics_stone_03.xml` |
| 4     | `data/entities/props/physics_stone_03.xml` |
| 5     | `data/entities/props/physics_stone_04.xml` |
| 6     | `data/entities/props/physics_stone_04.xml` |

#### `props`

This table contains paths to various interactive physics props.

| Index | Entity Path                               |
| :---- | :---------------------------------------- |
| 1     | `data/entities/props/physics_box_explosive.xml` |
| 2     | `data/entities/props/physics_barrel_oil.xml` |
| 3     | `data/entities/props/physics_seamine.xml` |
| 4     | `data/entities/props/physics/minecart.xml` |

### Randomization Functions

The script utilizes `ProceduralRandomi` and `ProceduralRandomf` for generating random numbers, ensuring varied outcomes each time the script is executed. These functions take positional arguments to ensure that the randomization is consistent for a given location but different across different locations.

*   `ProceduralRandomi(x, y, min, max)`: Generates a random integer between `min` and `max` (inclusive) based on the provided coordinates.
*   `ProceduralRandomf(x, y)`: Generates a random float between 0.0 and 1.0 based on the provided coordinates.

### Initial Position Offset

The script slightly offsets the initial horizontal position of the spawned entities by subtracting 5 from `pos_x`. This can influence the starting point of the spawned cluster.

```lua
local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
pos_x = pos_x - 5 -- Initial horizontal offset
```