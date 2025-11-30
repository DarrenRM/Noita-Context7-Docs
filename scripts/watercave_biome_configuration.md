---
title: Watercave Biome Configuration
category: scripts
---

# Watercave Biome Configuration

This document outlines the configuration for the Watercave biome in Noita, focusing on its entity spawning and layout generation.

## Core Biome Functions

The Watercave biome utilizes default functions for initialization and layout, with specific spawn functions registered for different events.

### Registered Spawn Functions

| Event Hash | Function Name | Description |
|---|---|---|
| `0xffffeedd` | `init` | Default initialization function. |
| `0xffffb539` | `random_layout` | Function to load a random biome layout. |

## Entity Spawning

The biome defines specific probabilities and entities for spawning smaller enemies.

### `g_small_enemies` Table

This table defines the distribution of smaller enemies within the Watercave biome.

| Attribute | Value | Description |
|---|---|---|
| `total_prob` | `0` | Base probability for spawning. |
| `prob` | `0.1` | Probability of spawning the entity. |
| `min_count` | `0` or `1` | Minimum number of entities to spawn. |
| `max_count` | `0` or `2` | Maximum number of entities to spawn. |
| `entity` | `string` | Path to the entity XML file. |

**Key Entities:**

*   `data/entities/animals/slimeshooter.xml`
*   `data/entities/animals/acidshooter.xml`
*   `data/entities/animals/giantshooter.xml`
*   `data/entities/animals/lasershooter.xml`

### `spawn_small_enemies(x, y)`

This function is responsible for spawning the entities defined in the `g_small_enemies` table at the specified coordinates.

### `spawn_items(x, y)`

Spawns a health pickup at the given coordinates.

*   `data/entities/items/pickup/heart.xml`

### `spawn_props(x, y)`

Spawns a full health pickup at the given coordinates.

*   `data/entities/items/pickup/heart_fullhp.xml`

## Layout Generation

The `random_layout` function is used to procedurally generate the visual structure of the Watercave biome.

### `random_layout(x, y)`

This function selects a random layout from a set of pre-defined pixel scenes based on the biome's coordinates.

*   It uses `ProceduralRandom` to determine which layout to load.
*   The loaded scenes are located in `data/biome_impl/watercave_layout_*.png`.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this script, indicating they are either placeholders or handled by other scripts.

*   `spawn_big_enemies( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `init( x, y, w, h )`