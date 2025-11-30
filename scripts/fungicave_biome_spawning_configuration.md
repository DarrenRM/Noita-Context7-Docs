---
title: Fungicave Biome Spawning Configuration
category: scripts/
---

# Fungicave Biome Spawning Configuration

This document details the spawning configurations for the Fungicave biome in Noita, focusing on enemy types, items, and environmental elements.

## Core Biome Functions

The script registers several functions to be called at specific points during level generation, triggered by tile colors.

*   **`init(x, y, w, h)`**: Handles the initialization of the biome, including the potential spawning of a secret portal target if the player-defined portal position falls within the biome's bounds.
*   **`spawn_robots(x, y)`**: Spawns robotic entities within the biome.
*   **`spawn_nest(x, y)`**: Spawns various types of nests.
*   **`spawn_physics_fungus(x, y)`**: Spawns physics-based fungal props.

## Enemy Spawning Tables

These tables define the probability and count of various enemies that can spawn within the Fungicave biome.

### Small Enemies (`g_small_enemies`)

This table lists the smaller enemy types and their spawn probabilities.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| 0.2         | 0         | 0         | (No spawn)                                 |
| 0.3         | 1         | 3         | `data/entities/animals/zombie.xml`         |
| 0.1         | 1         | 2         | `data/entities/animals/slimeshooter.xml`   |
| 0.4         | 1         | 3         | `data/entities/animals/rat.xml`            |
| 0.3         | 1         | 3         | `data/entities/animals/fungus.xml`         |
| 0.05        | 1         | 2         | `data/entities/animals/acidshooter.xml`    |
| 0.1         | 1         | 2         | `data/entities/animals/ant.xml`            |
| 0.1         | 2         | 4         | `data/entities/animals/blob.xml`           |
| 0.09        | 1         | 2         | `data/entities/animals/tentacler.xml`      |
| 0.11        | 1         | 2         | `data/entities/animals/tentacler_small.xml`|
| 0.08        | 1         | 1         | Multiple tentacler types                   |
| 0.1         | 1         | 2         | `data/entities/animals/wizard_tele.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/wizard_dark.xml`    |
| 0.07        | 1         | 1         | `data/entities/animals/wizard_swapper.xml` |
| 0.1         | 1         | 1         | `data/entities/animals/scavenger_invis.xml`|
| 0.05        | 1         | 1         | Multiple frog types                        |

### Big Enemies (`g_big_enemies`)

This table lists the larger enemy types and their spawn probabilities.

| Probability | Min Count | Max Count | Entity                                   | NG+ Level |
| :---------- | :-------- | :-------- | :--------------------------------------- | :-------- |
| 0.7         | 0         | 0         | (No spawn)                               |           |
| 0.05        | 1         | 2         | `data/entities/animals/thundermage.xml`  |           |
| 0.4         | 1         | 3         | `data/entities/animals/fungus.xml`       |           |
| 0.2         | 1         | 2         | `data/entities/animals/acidshooter.xml` |           |
| 0.1         | 1         | 1         | `data/entities/animals/giantshooter.xml` |           |
| 0.1         | 3         | 5         | `data/entities/animals/blob.xml`         |           |
| 0.05        | 1         | 1         | `data/entities/animals/bigzombie.xml`    |           |
| 0.05        | 1         | 1         | `data/entities/animals/wizard_poly.xml`  |           |
| 0.1         | 1         | 1         | `data/entities/animals/maggot.xml`       |           |
| 0.2         | 1         | 1         | `data/entities/animals/alchemist.xml`    |           |
| 0.04        | 1         | 1         | `data/entities/animals/fungus_big.xml`   |           |
| 0.04        | 1         | 1         | `data/entities/animals/wizard_neutral.xml`|           |
| 0.06        | 1         | 1         | `data/entities/animals/wizard_twitchy.xml`|           |
| 0.01        | 1         | 1         | Multiple fungus types                    |           |
| 0.1         | 1         | 1         | `data/entities/animals/drone_shield.xml` | 2         |
| 0.01        | 1         | 1         | `data/entities/animals/slimespirit.xml`  |           |
| 0.01        | 1         | 1         | `data/entities/animals/confusespirit.xml`|           |

## Item Spawning

### Items (`g_items`)

This table defines the probability of spawning specific items.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0           | 0         | 0         | (No spawn)                           |
| 5           | 1         | 1         | `data/entities/items/wand_unshuffle_02.xml` |
| 5           | 1         | 1         | `data/entities/items/wand_unshuffle_01.xml` |

## Miscellaneous Spawns

### Nests (`g_nest`)

Controls the spawning of various enemy nests.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0.5         | 1         | 1         | `data/entities/buildings/flynest.xml`|
| 0.5         | 1         | 1         | `data/entities/buildings/spidernest.xml`|

### Physics Fungi (`g_physics_fungi`)

Defines the types and probabilities of physics-based fungal props.

| Probability | Min Count | Max Count | Entity                                     |
| :---------- | :-------- | :-------- | :----------------------------------------- |
| 1.0         | 0         | 0         | (No spawn)                                 |
| 1.0         | 1         | 1         | `data/entities/props/physics_fungus_small.xml` |
| 1.0         | 1         | 1         | `data/entities/props/physics_fungus.xml`     |
| 0.5         | 1         | 1         | `data/entities/props/physics_fungus_big.xml` |

### Robots (`g_robots`)

Configuration for spawning robotic enemies.

| Probability | Min Count | Max Count | Entity                               |
| :---------- | :-------- | :-------- | :----------------------------------- |
| 0.5         | 0         | 0         | (No spawn)                           |
| 0.5         | 1         | 1         | `data/entities/animals/roboguard.xml`|
| 0.5         | 1         | 2         | `data/entities/animals/drone_physics.xml`|
| 0.01        | 1         | 1         | `data/entities/animals/assassin.xml` |

### Props (`g_props`)

General props that can spawn in the biome.

| Probability | Min Count | Max Count | Entity                                       |
| :---------- | :-------- | :-------- | :------------------------------------------- |
| 0.5         | 0         | 0         | (No spawn)                                   |
| 0.5         | 1         | 1         | `data/entities/props/physics_barrel_radioactive.xml` |

### Ghost Lamp (`g_ghostlamp`)

Specific configuration for spawning ghostly chain torches.

| Probability | Min Count | Max Count | Offset Y | Entity                                       |
| :---------- | :-------- | :-------- | :------- | :------------------------------------------- |
| 1.0         | 1         | 1         | 10       | `data/entities/props/physics_chain_torch_ghostly.xml` |

### Candles (`g_candles`)

Defines the types of candles that can spawn.

| Probability | Min Count | Max Count | Entity                           |
| :---------- | :-------- | :-------- | :------------------------------- |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_1.xml` |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_2.xml` |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_3.xml` |

### Potions (`g_potions`)

Currently, this table is empty and does not spawn any potion-related entities.

| Probability | Min Count | Max Count | Entity |
| :---------- | :-------- | :-------- | :----- |
| 0.5         | 1         | 1         | (No spawn) |

## Helper Functions

The script also includes several helper functions for spawning specific elements:

*   **`spawn_small_enemies(x, y)`**: Calls the `spawn` function with `g_small_enemies`.
*   **`spawn_big_enemies(x, y)`**: Calls the `spawn` function with `g_big_enemies`.
*   **`spawn_items(x, y)`**: Spawns a wand altar with a small chance.
*   **`spawn_nest(x, y)`**: Calls the `spawn` function with `g_nest`.
*   **`spawn_robots(x, y)`**: Calls the `spawn` function with `g_robots`.
*   **`spawn_props(x, y)`**: Calls the `spawn` function with `g_props`.
*   **`spawn_potion_altar(x, y)`**: Spawns a potion altar.
*   **`spawn_physics_fungus(x, y)`**: Calls the `spawn` function with `g_physics_fungi`.

The following functions are defined but do not contain any implementation: `spawn_lamp`, `load_pixel_scene`, `load_pixel_scene2`, `spawn_props2`, `spawn_props3`, `spawn_unique_enemy`, `spawn_unique_enemy2`, `spawn_unique_enemy3`, `spawn_ghostlamp`, `spawn_candles`.