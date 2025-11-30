---
title: Sandcave Biome Configuration
category: scripts/
---

# Sandcave Biome Configuration

This document details the configuration for the Sandcave biome in Noita, focusing on enemy spawns, item placements, and environmental elements.

## Core Biome Settings

The Sandcave biome utilizes default functions for level generation and entity spawning.

-   **CHEST\_LEVEL**: Defines the difficulty level for chests found within the biome. Set to `3`.
-   **dofile\_once**: Includes essential helper scripts for director logic and biome-specific functions.
    -   `data/scripts/director_helpers.lua`
    -   `data/scripts/biome_scripts.lua`
-   **RegisterSpawnFunction**: Registers specific functions to be called during biome generation.
    -   `0xffC8C800`: Maps to `spawn_lamp2`.
    -   `0xffDC0060`: Maps to `spawn_props4`.

## Enemy Spawning Tables

These tables define the probabilities and types of enemies that can spawn within the Sandcave biome.

### `g_small_enemies`

This table governs the spawning of smaller enemy types.

| Attribute   | Description