---
title: Mountain Tree Biome Script
category: scripts/
---

# Mountain Tree Biome Script

This script defines the spawning behavior and special functions for the Mountain Tree biome in Noita. It registers various spawn functions and defines tables for enemy and item probabilities.

## Core Functionality

This script relies on `director_helpers.lua` and `biome_scripts.lua` for core Noita director and biome functionalities.

### Registered Spawn Functions

These functions are called by the game director to spawn specific entities or trigger events at designated locations.

*   `RegisterSpawnFunction( 0xff3461C7, "spawn_book" )`: Registers a function to spawn books.
*   `RegisterSpawnFunction( 0xff9393d2, "spawn_egg" )`: Registers a function to spawn eggs.
*   `RegisterSpawnFunction( 0xff3482c7, "spawn_ocarina" )`: Registers a function to spawn ocarinas.
*   `RegisterSpawnFunction( 0xff31d0b4, "spawn_secret" )`: Registers a function to spawn secret items.
*   `RegisterSpawnFunction( 0xffc2d0b4, "spawn_pillars" )`: Registers a function to spawn pillars.

## Entity Spawning Tables

These tables define the probability and count of various entities that can spawn within the biome.

### `g_small_enemies`

Defines the probability of spawning smaller enemies.

| Attribute   | Value                               | Description                                                              |
| :---------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                 | Total probability, typically calculated dynamically.                     |
| `prob`      | `1.5`                               | Probability for this entry.                                              |
| `min_count` | `0`                                 | Minimum number of entities to spawn.                                     |
| `max_count` | `0`                                 | Maximum number of entities to spawn.                                     |
| `entity`    | `""`                                | Entity path. Empty string indicates no spawn at this probability level.  |
| `prob`      | `0.3`                               | Probability for this entry.                                              |
| `min_count` | `1`                                 | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                 | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/zombie.xml"`| Spawns a zombie.                                                         |
| `prob`      | `0.05`                              | Probability for this entry.                                              |
| `min_count` | `1`                                 | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                 | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/miner.xml"` | Spawns a miner.                                                          |
| `prob`      | `0.025`                             | Probability for this entry.                                              |
| `min_count` | `1`                                 | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                 | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/rat.xml"`   | Spawns a rat.                                                            |

### `g_items`

Defines the probability of spawning various items.

| Attribute   | Value                                       | Description                                                              |
| :---------- | :------------------------------------------ | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                         | Total probability, typically calculated dynamically.                     |
| `prob`      | `1.2`                                       | Probability for this entry.                                              |
| `min_count` | `0`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `0`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `""`                                        | Entity path. Empty string indicates no spawn at this probability level.  |
| `prob`      | `0.01`                                      | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/grenadelauncher.xml"` | Spawns a Grenade Launcher.                                               |
| `prob`      | `0.1`                                       | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/machinegun.xml"`      | Spawns a Machine Gun.                                                    |
| `prob`      | `0.001`                                     | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/opgun.xml"`           | Spawns an OP Gun.                                                        |
| `prob`      | `0.0001`                                    | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/lightninggun.xml"`    | Spawns a Lightning Gun.                                                  |
| `prob`      | `0.02`                                      | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/rocketlauncher.xml"`  | Spawns a Rocket Launcher.                                                |
| `prob`      | `0.1`                                       | Probability for this entry.                                              |
| `min_count` | `1`                                         | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                         | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/shotgun.xml"`         | Spawns a Shotgun.                                                        |

### `g_unique_enemy`

Defines the probability of spawning unique or special enemies.

| Attribute   | Value                                         | Description                                                              |
| :---------- | :-------------------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                           | Total probability, typically calculated dynamically.                     |
| `prob`      | `0.5`                                         | Probability for this entry.                                              |
| `min_count` | `1`                                           | Minimum number of entities to spawn.                                     |
| `max_count` | `3`                                           | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/slimeshooter.xml"`    | Spawns a Slime Shooter.                                                  |
| `prob`      | `0.3`                                         | Probability for this entry.                                              |
| `min_count` | `1`                                           | Minimum number of entities to spawn.                                     |
| `max_count` | `2`                                           | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/acidshooter.xml"`    | Spawns an Acid Shooter.                                                  |
| `prob`      | `0.1`                                         | Probability for this entry.                                              |
| `min_count` | `1`                                           | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                           | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/animals/giantshooter.xml"`  | Spawns a Giant Shooter.                                                  |

### `g_ghostlamp`

Defines the probability of spawning a ghostly lamp.

| Attribute   | Value                                               | Description                                                              |
| :---------- | :-------------------------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                                 | Total probability, typically calculated dynamically.                     |
| `prob`      | `1.0`                                               | Probability for this entry.                                              |
| `min_count` | `1`                                                 | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                                 | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/props/physics_chain_torch_ghostly.xml"` | Spawns a ghostly physics chain torch.                                    |

### `g_stash`

Defines the probability of spawning items from a stash.

| Attribute   | Value                                | Description                                                              |
| :---------- | :----------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                  | Total probability, typically calculated dynamically.                     |
| `prob`      | `0.4`                                | Probability for this entry.                                              |
| `min_count` | `1`                                  | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                  | Maximum number of entities to spawn.                                     |
| `entity`    | `""`                                 | Entity path. Empty string indicates no spawn at this probability level.  |
| `prob`      | `0.6`                                | Probability for this entry.                                              |
| `min_count` | `1`                                  | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                  | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/pickup/heart.xml"` | Spawns a heart pickup.                                                   |

### `g_candles`

Defines the probability of spawning different types of candles.

| Attribute   | Value                                    | Description                                                              |
| :---------- | :--------------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                      | Total probability, typically calculated dynamically.                     |
| `prob`      | `0.33`                                   | Probability for this entry.                                              |
| `min_count` | `1`                                      | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                      | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/props/physics_candle_1.xml"` | Spawns a type 1 physics candle.                                          |
| `prob`      | `0.33`                                   | Probability for this entry.                                              |
| `min_count` | `1`                                      | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                      | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/props/physics_candle_2.xml"` | Spawns a type 2 physics candle.                                          |
| `prob`      | `0.33`                                   | Probability for this entry.                                              |
| `min_count` | `1`                                      | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                      | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/props/physics_candle_3.xml"` | Spawns a type 3 physics candle.                                          |

### `g_lamp`

Defines the probability of spawning a mining lamp.

| Attribute   | Value                                      | Description                                                              |
| :---------- | :----------------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                        | Total probability, typically calculated dynamically.                     |
| `prob`      | `0.7`                                      | Probability for this entry.                                              |
| `min_count` | `1`                                        | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                        | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/props/physics_mining_lamp.xml"` | Spawns a physics mining lamp.                                            |

### `g_egg`

Defines the probability of spawning different types of eggs.

| Attribute   | Value                                  | Description                                                              |
| :---------- | :------------------------------------- | :----------------------------------------------------------------------- |
| `total_prob`| `0`                                    | Total probability, typically calculated dynamically.                     |
| `prob`      | `0.4`                                  | Probability for this entry.                                              |
| `min_count` | `1`                                    | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                    | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/pickup/egg_worm.xml"` | Spawns a worm egg.                                                       |
| `prob`      | `0.02`                                 | Probability for this entry.                                              |
| `min_count` | `1`                                    | Minimum number of entities to spawn.                                     |
| `max_count` | `1`                                    | Maximum number of entities to spawn.                                     |
| `entity`    | `"data/entities/items/pickup/egg_purple.xml"` | Spawns a purple egg.                                                     |

## Biome Specific Functions

These functions are called by the game director based on the registered spawn functions.

### `spawn_small_enemies(x, y)`

Spawns small enemies from the `g_small_enemies` table at the given coordinates.

### `spawn_big_enemies(x, y)`

Placeholder function for spawning big enemies. Currently does not spawn anything.

### `spawn_items(x, y)`

Placeholder function for spawning items. Currently does not spawn anything.

### `spawn_unique_enemy(x, y)`

Spawns unique enemies from the `g_unique_enemy` table at the given coordinates.

### `spawn_lamp(x, y)`

Spawns a mining lamp from the `g_lamp` table at the given coordinates, slightly offset upwards.

### `spawn_props(x, y)`

Placeholder function for spawning props. Currently does not spawn anything.

### `spawn_potions(x, y)`

Placeholder function for spawning potions. Currently does not spawn anything.

### `spawn_book(x, y)`

Loads a "book\_tree.xml" entity at the given coordinates.

### `spawn_egg(x, y)`

Spawns eggs from the `g_egg` table at the given coordinates.

### `spawn_ocarina(x, y)`

Spawns a Kantele and multiple "item action entities" representing musical notes at the given coordinates. If the current month is December and the day is between the 23rd and 27th, it also spawns a holiday workshop.

### `spawn_secret(x, y)`

Loads a "greed\_curse.xml" entity at the given coordinates.

### `spawn_pillars(x, y)`

Generates a series of pillars with varying visual elements and potential special effects based on persistent player flags. Each pillar has a base structure and can have additional parts loaded with specific textures (e.g., `pillar_part_material.png`, `pillar_part_fade.png`, `pillar_part_misc_chest_rain.png`). The specific visual elements loaded for the upper parts of the pillars are determined by checking for persistent flags like "misc\_chest\_rain", "essence\_fire", "progress\_ending0", "miniboss\_dragon", etc. The top of each pillar also has a randomly selected decorative end piece.