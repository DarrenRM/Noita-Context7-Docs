---
title: Fungi Forest Biome Configuration
category: biome
---

# Fungi Forest Biome Configuration

This document details the configuration for the Fungi Forest biome in Noita, focusing on entity spawning and biome-specific elements.

## Core Biome Functions

The Fungi Forest biome utilizes several core functions for its initialization and entity spawning.

*   **`init(x, y, w, h)`**: The primary initialization function for the biome.
*   **`spawn_small_enemies(x, y)`**: Spawns smaller enemy entities within the biome.
*   **`spawn_big_enemies(x, y)`**: Spawns larger, more formidable enemy entities.
*   **`spawn_items(x, y)`**: Handles the spawning of items, including wands and potentially other gameplay-affecting objects.
*   **`spawn_nest(x, y)`**: A placeholder function, currently not implementing any specific spawning logic.
*   **`spawn_props(x, y)`**: Spawns environmental props and interactive objects.
*   **`spawn_fungitrap(x, y)`**: Spawns fungitrap entities, a unique hazard of this biome.
*   **`spawn_potion_altar(x, y)`**: Spawns potion altars, often associated with healing or buffs.
*   **`spawn_physics_fungus(x, y)`**: Spawns various types of physics-enabled fungi.
*   **`spawn_physics_acid_fungus(x, y)`**: Spawns acid-infused physics fungi.
*   **`spawn_vines(x, y)`**: Spawns vine entities, which can be part of the biome's terrain or hazards.

## Entity Spawning Tables

The following tables define the probability and count for various entities that can spawn within the Fungi Forest biome.

### Small Enemies (`g_small_enemies`)

This table defines the distribution of smaller enemy types.

| Probability | Min Count | Max Count | Entity                                    |
| :---------- | :-------- | :-------- | :---------------------------------------- |
| 2.2         | 0         | 0         | (No spawn - air)                          |
| 0.5         | 1         | 3         | `data/entities/animals/fungus.xml`        |
| 0.5         | 1         | 2         | `data/entities/animals/fungus_big.xml`    |
| 0.1         | 1         | 2         | `data/entities/animals/ant.xml`           |
| 0.2         | 2         | 4         | `data/entities/animals/blob.xml`          |
| 0.1         | 2         | 4         | `data/entities/animals/frog_big.xml`      |
| 0.08        | 1         | 1         | `data/entities/animals/fungus_giga.xml`   |

### Big Enemies (`g_big_enemies`)

This table defines the distribution of larger and more dangerous enemy types.

| Probability | Min Count | Max Count | Entity