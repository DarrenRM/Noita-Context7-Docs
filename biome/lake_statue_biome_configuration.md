---
title: Lake Statue Biome Configuration
category: biome/
---

# Lake Statue Biome Configuration

This document details the configuration for the "Lake Statue" biome in Noita, focusing on its entity spawning and special behaviors.

## Core Biome Functions

The `lake_statue.lua` script registers several functions to be called at specific game events, primarily for spawning entities and managing biome-specific logic.

### Registered Spawn Functions

These functions are triggered by the game's director system based on specific event IDs.

| Event ID | Function Name             | Description                                    |
| :------- | :------------------------ | :--------------------------------------------- |
| `0xffffeedd` | `init`                    | Initializes the biome.                         |
| `0xfff21df0` | `load_building_stash`     | Loads building stash entities.                 |
| `0xffb4a00a` | `spawn_fish`              | Spawns fish entities.                          |
| `0xffb40b76` | `spawn_bigfish`           | Spawns larger fish entities.                   |
| `0xff3ae124` | `spawn_small_animals`     | Spawns small animal entities.                  |
| `0xff31d0b4` | `spawn_essence`           | Spawns essence pickups.                        |
| `0xff30D14E` | `spawn_secret_checker`    | Spawns a material checker for secrets.         |
| `0xff57ac68` | `spawn_spirit_spawner`    | Spawns a spirit spawner entity.                |

## Entity Spawning Tables

These tables define the probabilities and types of entities that can be spawned within the biome.

### `g_fish` Table

Controls the spawning of various fish entities.

| Attribute   | Value                               | Description                                    |
| :---------- | :---------------------------------- | :--------------------------------------------- |
| `total_prob`| `0`                                 | Total probability (likely calculated dynamically). |
| `prob`      | `1.0`                               | Probability of this entry spawning.            |
| `min_count` | `1`                                 | Minimum number of entities to spawn.           |
| `max_count` | `1`                                 | Maximum number of entities to spawn.           |
| `entity`    | `"data/entities/animals/fish.xml"`  | Path to the fish entity XML.                   |

### `g_small_animals` Table

Defines the pool of small animals that can spawn.

| Attribute   | Value                                     | Description                                    |
| :---------- | :---------------------------------------- | :--------------------------------------------- |
| `total_prob`| `0`                                       | Total probability (likely calculated dynamically). |
| `prob`      | `1.0`                                     | Probability of this entry spawning.            |
| `min_count` | `1`                                       | Minimum number of entities to spawn.           |
| `max_count` | `1`                                       | Maximum number of entities to spawn.           |
| `entity`    | `""`                                      | No entity (placeholder).                       |
| `entity`    | `"data/entities/animals/deer.xml"`        | Path to the deer entity XML.                   |
| `entity`    | `"data/entities/animals/duck.xml"`        | Path to the duck entity XML.                   |
| `entity`    | `"data/entities/animals/elk.xml"`         | Path to the elk entity XML.                    |
| `entity`    | `"data/entities/animals/sheep.xml"`       | Path to the sheep entity XML.                  |
| `entity`    | `"data/entities/animals/wolf.xml"`        | Path to the wolf entity XML (low probability). |

### `g_hiisi` Table

Configures the spawning of various "Hiisi" (enemy) types. This table is extensive and includes multiple variations and combinations.

| Attribute   | Value