---
title: Overworld Desert Prop Spawner
category: scripts
---

# Overworld Desert Prop Spawner

This script is responsible for spawning various props within the overworld desert biome. It includes logic to prevent spawning in specific areas and uses a weighted probability system to select which prop to spawn.

## Core Functionality

The primary purpose of this script is to dynamically place decorative or functional entities within the desert environment.

## Spawning Conditions

The script enforces specific conditions to control where props are spawned:

*   **X-coordinate range:** `pos_x > 7110 and pos_x < 7640`
*   **Y-coordinate limit:** `pos_y > 100` (props will not spawn if the Y-coordinate is 100 or below)

If these conditions are not met, the spawner entity is immediately killed, and no prop is spawned.

## Available Props and Probabilities

The script defines a list of potential props to spawn, each with an associated probability. The `pick_random_from_table_weighted` function is used to select one based on these probabilities.

| File                                       | Probability | Description                               |
| :----------------------------------------- | :---------- | :---------------------------------------- |
| `data/entities/props/overworld/sand_pile_01.xml` | `1.0`       | A basic sand pile prop.                   |
| `data/entities/props/overworld/sand_pile_02.xml` | `1.0`       | Another variation of a sand pile prop.    |
| `data/entities/props/overworld/desert_ruins_spawner.xml` | `0.6`       | Spawns desert ruins structures.           |

## Execution Flow

1.  The script retrieves the current entity's ID and its world position (`pos_x`, `pos_y`).
2.  It checks if the entity's position meets the spawning conditions. If not, the entity is killed.
3.  If conditions are met, it randomly selects a prop from the `props` table based on weighted probabilities.
4.  The selected prop's XML file is loaded at the spawner's position.
5.  Finally, the spawner entity itself is killed, as its task is complete.