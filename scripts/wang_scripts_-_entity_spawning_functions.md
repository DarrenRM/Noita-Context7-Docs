---
title: Wang Scripts - Entity Spawning Functions
category: scripts
---

# Wang Scripts - Entity Spawning Functions

This document details the functions available in `wang_scripts.csv` for spawning various entities within Noita. These scripts are primarily used for defining what can appear in different game contexts.

## Key Attributes

The `wang_scripts.csv` file uses a simple comma-separated format. Each line represents a spawnable entity or group of entities, defined by the following attributes:

*   **COLOR**: A hexadecimal color code (RGBA) associated with the script. This is often used for visual identification in the game's internal data.
*   **FUNCTION\_NAME**: The name of the Lua function that is called to perform the spawning action. This is the core identifier for the script's purpose.
*   **IN\_PATH\_MIN / IN\_PATH\_MAX**: Minimum and maximum values for a parameter related to spawning within a specific path or context. A value of `-1` typically indicates no specific limit or that the parameter is not used for this function.
*   **OUTSIDE\_PATH\_MIN / OUTSIDE\_PATH\_MAX**: Minimum and maximum values for a parameter related to spawning outside a specific path or context. Similar to `IN_PATH`, `-1` usually means the parameter is not applicable or limited.

## Core Spawning Functions

The following table lists the most common and important spawning functions, along with their associated colors and general purpose.

| COLOR    | FUNCTION\_NAME              | IN\_PATH\_MIN | IN\_PATH\_MAX | OUTSIDE\_PATH\_MIN | OUTSIDE\_PATH\_MAX | Description                                     |
| :------- | :-------------------------- | :------------ | :------------ | :----------------- | :----------------- | :---------------------------------------------- |
| `ffff0000` | `spawn_small_enemies`       | -1            | -1            | -1                 | -1                 | Spawns various small enemy types.               |
| `ff800000` | `spawn_big_enemies`         | -1            | -1            | -1                 | -1                 | Spawns larger, more formidable enemy types.     |
| `ff00ff00` | `spawn_items`               | -1            | -1            | -1                 | -1                 | Spawns collectible items (e.g., gold, hearts).  |
| `ffc88d1a` | `spawn_props`               | -1            | -1            | -1                 | -1                 | Spawns environmental props and decorations.     |
| `ffc88000` | `spawn_props2`              | -1            | -1            | -1                 | -1                 | Alternative function for spawning props.        |
| `ffc80040` | `spawn_props3`              | -1            | -1            | -1                 | -1                 | Another alternative function for spawning props. |
| `ffffff00` | `spawn_lamp`                | -1            | -1            | -1                 | -1                 | Spawns various types of lamps.                  |
| `ffff0aff` | `load_pixel_scene`          | -1            | -1            | -1                 | -1                 | Loads a pre-defined pixel scene.                |
| `ffFF0080` | `load_pixel_scene2`         | -1            | -1            | -1                 | -1                 | Alternative function for loading pixel scenes.  |
| `ffFF8000` | `spawn_unique_enemy`        | -1            | -1            | -1                 | -1                 | Spawns a specific, unique enemy.                |
| `ffbca0f0` | `spawn_potions`             | -1            | -1            | -1                 | -1                 | Spawns various types of potions.                |
| `ff50A0F0` | `spawn_wands`               | -3            | -3            | -4                 | -4                 | Spawns wands. The path parameters may influence rarity or type. |
| `ffffd171` | `spawn_orb`                 | -1            | -1            | -1                 | -1                 | Spawns a powerful orb.                          |
| `ffffd181` | `spawn_perk`                | -1            | -1            | -1                 | -1                 | Spawns a random perk.                           |
| `ffffff81` | `spawn_all_perks`           | -1            | -1            | -1                 | -1                 | Spawns all available perks.                     |
| `ffc7eb28` | `spawn_wand_trap`           | -1            | -1            | -1                 | -1                 | Spawns a wand trap.                             |
| `ff6b4f9b` | `spawn_moon`                | -1            | -1            | -1                 | -1                 | Spawns a moon entity.                           |
| `ffd7b3e8` | `spawn_collapse`            | -1            | -1            | -1                 | -1                 | Triggers a collapse event.                      |

## Notes for Modding

*   The `IN_PATH` and `OUTSIDE_PATH` parameters are often used to control the *probability* or *intensity* of spawning. For many functions, `-1` indicates that these parameters are not actively used or are set to a default.
*   Modders can create new entries in this CSV or modify existing ones to change what entities appear in the game. This requires understanding the specific Lua functions called by `FUNCTION_NAME`.
*   The `COLOR` attribute is primarily for internal game organization and debugging; it doesn't directly affect gameplay mechanics.
*   For more advanced spawning logic, you would typically look into the Lua scripts themselves that are referenced by these `FUNCTION_NAME` entries.