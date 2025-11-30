---
title: Snowcave Secret Chamber Biome Script
category: scripts/biome
---

# Snowcave Secret Chamber Biome Script

This script defines the behavior and content for the secret chamber biome within the Snowcave. It handles loading the visual scene and spawning various entities.

## Core Functions

This script registers several spawn functions that are called by the game's director system.

-   `RegisterSpawnFunction( 0xff55AF8C, "spawn_skulls" )`: Registers a function to spawn skulls.
-   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the main initialization function for the biome.
-   `RegisterSpawnFunction( 0xff366178, "spawn_teleporter" )`: Registers a function to spawn a teleporter.

## Initialization

### `init(x, y, w, h)`

This function is called when the biome is initialized. It loads the pixel scene data for the secret chamber.

-   `LoadPixelScene( "data/biome_impl/snowcave/secret_chamber.png", "data/biome_impl/snowcave/secret_chamber_visual.png", x, y, "", true )`: Loads the biome's visual representation.

## Spawn Functions

These functions are responsible for populating the biome with specific entities.

### `spawn_lamp(x, y)`

Spawns a lamp entity using the `g_lamp` table.

### `spawn_skulls(x, y)`

Spawns skull entities using the `g_skulls` table.

### `spawn_teleporter(x, y)`

Loads a specific teleporter entity: `data/entities/buildings/teleport_snowcave_buried_eye_return.xml`.

## Entity Spawn Tables

These tables define the probabilities and entities to be spawned for different categories.

### `g_items`

Defines items that can be spawned.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 1           | 1         | 1         | `data/entities/items/wand_level_03.xml` |
| 1           | 1         | 1         | `data/entities/items/wand_unshuffle_02.xml` |

### `g_skulls`

Defines skull and bone props that can be spawned.

| Probability | Min Count | Max Count | Offset Y | Entity                                 |
| :---------- | :-------- | :-------- | :------- | :------------------------------------- |
| 6           | 1         | 1         | 0        | (Empty - no entity)                    |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_01.xml` |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_02.xml` |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_skull_03.xml` |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_01.xml`  |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_02.xml`  |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_03.xml`  |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_04.xml`  |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_05.xml`  |
| 0.5         | 1         | 1         | 0        | `data/entities/props/physics_bone_06.xml`  |

### `g_stones`

Defines stone piles and physics stones that can be spawned.

| Probability | Min Count | Max Count | Offset Y | Entity                                |
| :---------- | :-------- | :-------- | :------- | :------------------------------------ |
| 2           | 1         | 1         | 0        | `data/entities/props/stonepile.xml`   |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_stone_01.xml` |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_stone_02.xml` |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_stone_03.xml` |
| 1.5         | 1         | 1         | 0        | `data/entities/props/physics_stone_04.xml` |
| 4           | 1         | 1         | 0        | (Empty - no entity)                   |

### `g_lamp`

Defines lamp entities that can be spawned.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| 0.25        | 1         | 1         | (Empty - no entity)                        |
| 1.0         | 1         | 1         | `data/entities/props/physics/temple_lantern.xml` |

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, indicating they are either placeholders or handled by other scripts.

-   `spawn_shopitem( x, y )`
-   `spawn_small_enemies(x, y)`
-   `spawn_big_enemies(x, y)`
-   `spawn_unique_enemy(x, y)`
-   `spawn_props(x, y)`
-   `load_pixel_scene( x, y )`
-   `load_pixel_scene2( x, y )`
-   `spawn_items(x, y)`