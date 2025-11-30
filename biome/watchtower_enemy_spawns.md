---
title: Watchtower Enemy Spawns
category: biome
---

# Watchtower Enemy Spawns

This file defines the enemy spawn configurations for the Watchtower biome in Noita. It utilizes pre-defined spawn tables for "small" and "big" enemies, with specific variations and conditions.

## Core Spawn Functions

The file registers two primary spawn functions that can be called by the game engine:

*   `spawn_small_enemies2(x, y)`: Spawns enemies from the `g_small_enemies` table at the given coordinates.
*   `spawn_big_enemies2(x, y)`: Spawns enemies from the `g_big_enemies` table at the given coordinates.

## Enemy Spawn Tables

These tables define the probability and types of enemies that can spawn.

### `g_small_enemies`

This table governs the spawning of smaller enemy types.

| Attribute     | Description