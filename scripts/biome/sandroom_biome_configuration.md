---
title: Sandroom Biome Configuration
category: scripts/biome
---

# Sandroom Biome Configuration

This document outlines the configuration for the Sandroom biome in Noita, focusing on its spawning mechanics and entity placement.

## Core Biome Functions

The Sandroom biome utilizes a set of default functions for its initialization and entity spawning.

### Initialization

*   `init( x, y, w, h )`: This function is responsible for loading the visual representation of the Sandroom biome.
    *   It uses `LoadPixelScene` to load the `data/biome_impl/sandroom.png` file, defining the biome's layout and appearance.

### Entity Spawning

The biome registers specific functions for spawning certain entities at designated points.

*   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the `init` function to be called during biome initialization.
*   `RegisterSpawnFunction( 0xffbf262b, "spawn_metportal" )`: Registers the `spawn_metportal` function to handle the spawning of the biome's specific metarportal.

## Specific Entity Spawners

### Metaportal

*   `spawn_metportal( x, y )`: This function is called to place the biome's unique teleportation entity.
    *   It uses `EntityLoad` to instantiate `data/entities/buildings/teleport_sandroom.xml` at the given coordinates.

### Stash and Wands

*   `spawn_stash(x,y)`: Handles the potential spawning of a stash.
    *   It includes a procedural check (`ProceduralRandom(x,y) < 0.17`) to determine if a stash should spawn, with a 20% chance of air (no stash).
    *   If the check passes, it calls `entity_load_stash(x,y)`.
*   `spawn_wands(x, y)`: Manages the spawning of wands within the biome.
    *   It utilizes the `g_items` table to define the types and probabilities of items that can spawn.

## Item Spawning Configuration (`g_items`)

This table defines the items that can be spawned within the Sandroom biome, primarily focusing on wands.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| The sum of all probabilities, used for normalization (currently 0).      |
| `prob`      | The probability of this item spawning.                                   |
| `min_count` | The minimum number of this item to spawn.                                |
| `max_count` | The maximum number of this item to spawn.                                |
| `entity`    | The XML path to the entity to spawn.                                     |

### Key Item Entries:

*   **Air/No Spawn:**
    *   `prob: 0`, `min_count: 0`, `max_count: 0`, `entity: ""`
        *   Represents air or a condition where no item spawns.
*   **Wand Level 03:**
    *   `prob: 5`, `min_count: 1`, `max_count: 1`, `entity: "data/entities/items/wand_level_03.xml"`
        *   This is the primary wand spawn for this biome, with a probability of 5.

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation in this specific biome script. They are likely placeholders or intended for use in other biome configurations.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
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