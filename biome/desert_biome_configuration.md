---
title: Desert Biome Configuration
category: biome
---

---

# Desert Biome Configuration

This document outlines the configuration for the Desert biome in Noita, focusing on entity spawning and biome-specific logic.

## Core Biome Functions

The Desert biome utilizes default functions for initialization and spawning unless specific overrides are defined.

-   `dofile_once("data/scripts/director_helpers.lua")`: Includes helper functions for managing game directors.
-   `dofile_once("data/scripts/biome_scripts.lua")`: Includes general biome scripting functions.

### Spawn Function Registration

These functions are registered to be called by the game director at specific points or based on certain conditions.

-   `RegisterSpawnFunction( 0xff30D14E, "spawn_secret_checker" )`: Registers a function to check for secret areas.
-   `RegisterSpawnFunction( 0xff616602, "spawn_huussi_checker" )`: Registers a function to potentially spawn a "Huussi" structure.
-   `RegisterSpawnFunction( 0xffffeedd, "init" )`: Registers the main initialization function for the biome.

## Enemy Spawning Tables

These tables define the probabilities and counts for various enemies that can spawn within the Desert biome.

### `g_small_enemies`

This table defines the pool of smaller enemies that can spawn.

| Prob  | Min Count | Max Count | Entity                                   | Description                               |
| :---- | :-------- | :-------- | :--------------------------------------- | :---------------------------------------- |
| 1.5   | 0         | 0         | ""                                       | Placeholder for air; no spawns at this prob. |
| 0.1   | 1         | 1         | `data/entities/animals/scavenger_smg.xml` | Scavenger SMG                             |
| 0.1   | 1         | 1         | `data/entities/animals/scavenger_smg.xml` | Scavenger SMG                             |
| 0.05  | 1         | 1         | `data/entities/animals/scavenger_leader.xml` | Scavenger Leader                          |
| 0.05  | 1         | 1         | `data/entities/animals/tank.xml`         | Tank                                      |
| 0.001 | 1         | 1         | `data/entities/animals/tank_super.xml`   | Super Tank                                |

### `g_big_enemies`

This table defines the pool of larger enemies that can spawn.

| Prob  | Min Count | Max Count | Entity                                     | Description                               |
| :---- | :-------- | :-------- | :----------------------------------------- | :---------------------------------------- |
| 1.5   | 0         | 0         | ""                                         | Placeholder for air; no spawns at this prob. |
| 0.1   | 1         | 1         | `data/entities/animals/firemage.xml`       | Fire Mage                                 |
| 0.1   | 1         | 1         | `data/entities/animals/firemage_weak.xml`  | Weak Fire Mage                            |
| 0.05  | 1         | 1         | `data/entities/animals/thundermage.xml`    | Thunder Mage                              |
| 0.05  | 1         | 1         | `data/entities/animals/wizard_tele.xml`    | Teleporting Wizard                        |
| 0.05  | 1         | 1         | `data/entities/animals/wizard_returner.xml`| Returning Wizard                          |
| 0.05  | 1         | 1         | `data/entities/animals/wizard_dark.xml`    | Dark Wizard                               |
| 0.05  | 1         | 1         | `data/entities/animals/wizard_weaken.xml`  | Weakening Wizard                          |
| 0.001 | 1         | 1         | `data/entities/animals/enlightened_alchemist.xml` | Enlightened Alchemist                     |
| 0.05  | 1         | 1         | `data/entities/buildings/hpcrystal.xml`    | HP Crystal (building)                     |

### `g_unique_enemy`

This table defines unique or special enemies that can spawn.

| Prob  | Min Count | Max Count | Entity                               | Description                               |
| :---- | :-------- | :-------- | :----------------------------------- | :---------------------------------------- |
| 0.0   | 0         | 0         | ""                                   | Placeholder; no spawns at this prob.      |
| 0.5   | 1         | 3         | `data/entities/animals/slimeshooter.xml` | Slime Shooter                             |
| 0.3   | 1         | 2         | `data/entities/animals/acidshooter.xml`  | Acid Shooter                              |
| 0.1   | 1         | 1         | `data/entities/animals/giantshooter.xml` | Giant Shooter                             |

### `g_ghostlamp`

This table defines the spawning of ghost lamps.

| Prob  | Min Count | Max Count | Entity                                       | Description                               |
| :---- | :-------- | :-------- | :------------------------------------------- | :---------------------------------------- |
| 1.0   | 1         | 1         | `data/entities/props/physics_chain_torch_ghostly.xml` | Ghostly Physics Chain Torch               |

### `g_candles`

This table defines the spawning of various types of candles.

| Prob  | Min Count | Max Count | Entity                           | Description                               |
| :---- | :-------- | :-------- | :------------------------------- | :---------------------------------------- |
| 0.33  | 1         | 1         | `data/entities/props/physics_candle_1.xml` | Physics Candle 1                          |
| 0.33  | 1         | 1         | `data/entities/props/physics_candle_2.xml` | Physics Candle 2                          |
| 0.33  | 1         | 1         | `data/entities/props/physics_candle_3.xml` | Physics Candle 3                          |

## Miscellaneous Functions

These functions handle specific biome events and spawning logic.

### `init(x, y, w, h)`

The primary initialization function for the biome. It calls `parallel_check` to handle parallel processing of biome elements.

### `spawn_small_enemies(x, y)`

Spawns enemies based on the Y-coordinate. If `y < 1000`, it uses `g_small_enemies`; otherwise, it uses `g_big_enemies`.

### `spawn_big_enemies(x, y)`

Directly spawns enemies from the `g_big_enemies` table.

### `spawn_items(x, y)`

This function is currently a placeholder and does not spawn any items.

### `spawn_unique_enemy(x, y)`

Spawns a unique enemy from the `g_unique_enemy` table.

## Biome Logic Functions

These functions are triggered by specific game events or conditions within the biome.

### `spawn_secret_checker(x, y)`

Creates an `orb_room_materialchecker` entity at the given coordinates. This entity is configured to check for specific materials (e.g., "water") and, upon success, triggers the `material_area_checker_success` function.

-   **Material Check:** Configures the `MaterialAreaCheckerComponent` to look for "water" as `material1` and no specific `material2`.
-   **Lua Component:** Sets the `script_material_area_checker_success` to point to `data/scripts/biomes/desert.lua`, indicating that the `material_area_checker_success` function should be called upon a successful material check.

### `material_area_checker_success(x, y)`

This function is called when the `orb_room_materialchecker` successfully identifies the target materials.

-   **Screenshake:** Triggers a screenshake effect.
-   **Teleport Lake:** Spawns a `teleport_lake` entity.
-   **Game Message:** Displays an important game message indicating fast travel is available.

### `spawn_huussi_checker(x, y)`

Spawns a "Huussi" structure at the specified coordinates. This is likely used for specific biome events or challenges.