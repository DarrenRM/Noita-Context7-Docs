---
title: Endgame Biome Enemy and Prop Spawning Configuration
category: scripts
---

# Endgame Biome Enemy and Prop Spawning Configuration

This document details the configuration for enemy and prop spawning within the endgame biome of Noita, as defined in `data/scripts/biomes/endgame.lua`. It outlines the probabilities and types of entities that can appear in various spawn categories.

## Core Configuration

*   **`CHEST_LEVEL`**: Defines the base level for items spawned from chests. Currently set to `1`.
*   **`dofile_once`**: Includes essential helper functions for director and biome scripting.
    *   `data/scripts/director_helpers.lua`
    *   `data/scripts/biome_scripts.lua`
*   **`RegisterSpawnFunction`**: Registers a function for a specific biome ID.
    *   `0xff0000ff`: Associated with the `spawn_nest` function.

## Enemy Spawn Tables

These tables define the probability and count of different enemy types that can spawn in the endgame biome.

### `g_small_enemies`

Configuration for smaller enemy types.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `prob`      | Probability of this enemy type spawning.                                 |
| `min_count` | Minimum number of this enemy to spawn.                                   |
| `max_count` | Maximum number of this enemy to spawn.                                   |
| `entity`    | Path to the entity's XML definition.                                     |
| `spawn_check` | (Optional) A function that must return `true` for the entity to spawn. |

| Entity                                  | `prob` | `min_count` | `max_count` | Notes