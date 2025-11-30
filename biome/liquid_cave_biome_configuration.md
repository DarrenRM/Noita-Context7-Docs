---
title: Liquid Cave Biome Configuration
category: biome
---

---

# Liquid Cave Biome Configuration

This document details the configuration for the "Liquid Cave" biome in Noita, focusing on entity spawning and visual elements.

## Core Biome Functions

The script registers several functions to be called at specific points during biome generation and loading.

### Registered Spawn Functions

| Color Code | Function Name             | Description                                    |
|------------|---------------------------|------------------------------------------------|
| `0xffffeedd` | `init`                    | Default initialization function.               |
| `0xff00AC64` | `load_background_panel_big` | Loads large background panels.                 |
| `0xff967878` | `spawn_lasergun`          | Spawns a lasergun entity.                      |
| `0xff80FF5A` | `spawn_vines`             | Spawns vine entities.                          |
| `0xffc88dab` | `spawn_statues`           | Spawns statue entities.                        |

## Entity Spawn Lists

These tables define the probabilities and types of entities that can spawn within the Liquid Cave biome.

### `g_small_enemies`

Defines the pool of smaller enemies that can spawn.

| Attribute   | Description                                                              |
|-------------|--------------------------------------------------------------------------|
| `prob`      | Probability of this entry being selected.                                |
| `min_count` | Minimum number of entities to spawn.                                     |
| `max_count` | Maximum number of entities to spawn.                                     |
| `entity`    | Path to the entity XML file.                                             |
| `entities`  | Table of entity XML files for weighted spawning.                         |
| `ngpluslevel` | Minimum New Game+ level required for this entity to spawn.               |

**Key Entities:**

| Entity Path                               | Probability | Min Count | Max Count | NG+ Level |
|-------------------------------------------|-------------|-----------|-----------|-----------|
| `data/entities/animals/failed_alchemist.xml` | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/enlightened_alchemist.xml` | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/wizard_returner.xml` | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/wizard_neutral.xml`  | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/wizard_tele.xml`     | 0.1         | 1         | 1         | 1         |
| `data/entities/animals/wizard_dark.xml`     | 0.1         | 1         | 1         | 1         |

### `g_big_enemies`

Defines the pool of larger enemies that can spawn.

**Key Entities:**

| Entity Path                               | Probability | Min Count | Max Count | NG+ Level |
|-------------------------------------------|-------------|-----------|-----------|-----------|
| `data/entities/animals/failed_alchemist.xml` | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/enlightened_alchemist.xml` | 0.1         | 1         | 2         | N/A       |
| `data/entities/animals/shaman.xml`        | 0.08        | 1         | 1         | N/A       |
| `data/entities/animals/failed_alchemist_b.xml` | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/wizard_neutral.xml`  | 0.1         | 1         | 1         | N/A       |
| `data/entities/animals/wizard_twitchy.xml`  | 0.1         | 1         | 1         | 2         |
| `data/entities/animals/wizard_poly.xml`     | 0.1         | 1         | 1         | 2         |
| `data/entities/buildings/hpcrystal.xml`   | 0.05        | 1         | 1         | 1         |

### `g_lamp`

Defines the spawning of lamps.

| Entity Path                           | Probability | Min Count | Max Count | Offset Y |
|---------------------------------------|-------------|-----------|-----------|----------|
| `data/entities/props/physics_lantern.xml` | 1.5         | 1         | 2         | 4        |

### `g_props`

Defines the spawning of various props.

| Entity Path                       | Probability | Min Count | Max Count | Offset Y |
|-----------------------------------|-------------|-----------|-----------|----------|
| `data/entities/props/physics_bed.xml` | 0.8         | 1         | 1         | 5        |
| `data/entities/props/physics_crate.xml` | 0.1         | 1         | 1         | 0        |

### `g_props2`

Defines the spawning of banners.

| Entity Path                   | Probability | Min Count | Max Count | Offset Y |
|-------------------------------|-------------|-----------|-----------|----------|
| `data/entities/props/banner.xml` | 1.0         | 1         | 1         | 5        |

### `g_bottle`

Defines the spawning of bottles.

| Entity Path                               | Probability | Min Count | Max Count | Offset Y |
|-------------------------------------------|-------------|-----------|-----------|----------|
| `data/entities/props/physics_bottle_green.xml` | 0.3         | 1         | 1         | -5       |
| `data/entities/props/physics_bottle_red.xml`   | 0.3         | 1         | 1         | -5       |
| `data/entities/props/physics_bottle_blue.xml`  | 0.3         | 1         | 1         | -5       |
| `data/entities/props/physics_bottle_yellow.xml`| 0.2         | 1         | 1         | -5       |

### `g_chest`

Defines the spawning of chests.

| Entity Path                   | Probability | Min Count | Max Count |
|-------------------------------|-------------|-----------|-----------|
| `data/entities/items/chest.xml` | 0.2         | 1         | 1         |

### `g_vines`

Defines the spawning of vine entities.

| Entity Path                                       | Probability | Min Count | Max Count |
|---------------------------------------------------|-------------|-----------|-----------|
| `data/entities/verlet_chains/vines/verlet_vine.xml` | 0.4         | 1         | 1         |
| `data/entities/verlet_chains/vines/verlet_vine_long.xml` | 0.3         | 1         | 1         |
| `data/entities/verlet_chains/vines/verlet_vine_short.xml` | 0.5         | 1         | 1         |
| `data/entities/verlet_chains/vines/verlet_vine_shorter.xml` | 0.5         | 1         | 1         |

### `g_statues`

Defines the spawning of various statue entities.

| Entity Path                                     | Probability | Min Count | Max Count |
|-------------------------------------------------|-------------|-----------|-----------|
| `data/entities/props/statues/statue_rock_01.xml`  | 0.2         | 1         | 1         |
| `data/entities/props/statues/statue_rock_02.xml`  | 0.2         | 1         | 1         |
| ... (other statue_rock_XX.xml entries)          | ...         | ...       | ...       |
| `data/entities/buildings/statue_trap_right.xml` | 0.1         | 1         | 1         |
| `data/entities/buildings/statue_trap_left.xml`  | 0.1         | 1         | 1         |

## Visual Elements

These tables define the visual components of the biome, including materials and background elements.

### `g_pixel_scene_01`

Defines container elements with associated liquids.

| Attribute        | Description