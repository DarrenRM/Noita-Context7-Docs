---
title: Vault Frozen Biome Configuration
category: biome
---

# Vault Frozen Biome Configuration

This document details the configuration for the "Vault Frozen" biome in Noita, focusing on the entities and environmental elements that can spawn within it.

## Core Biome Functions

The `vault_frozen.lua` script registers various spawn functions that are called by the game's director system to populate the biome. These functions are triggered by specific color codes within the biome's level data.

### Registered Spawn Functions

| Color Code | Function Name      | Description                               |
| :--------- | :----------------- | :---------------------------------------- |
| `0xff400000` | `spawn_robots`     | Spawns robot entities.                    |
| `0xff00AC64` | `load_pixel_scene4`| Loads a specific pixel scene.             |
| `0xff01a1fa` | `spawn_turret`     | Spawns turret entities.                   |
| `0xff80FF5A` | `spawn_vines`      | Spawns vine-like structures.              |
| `0xff504B64` | `spawn_machines`   | Spawns various machines.                  |
| `0xffBE8246` | `spawn_pipes_hor`  | Spawns horizontal pipe segments.          |
| `0xffBE8264` | `spawn_pipes_turn_right` | Spawns right-turning pipe segments. |
| `0xffBE8282` | `spawn_pipes_turn_left`  | Spawns left-turning pipe segments.  |
| `0xffBE82A0` | `spawn_pipes_ver`  | Spawns vertical pipe segments.            |
| `0xffBE82BE` | `spawn_pipes_cross`| Spawns cross-shaped pipe segments.        |
| `0xffc78f20` | `spawn_barricade`  | Spawns barricade structures.              |

## Enemy Spawning Tables

The biome defines two primary tables for enemy spawning: `g_small_enemies` and `g_big_enemies`. Each entry in these tables specifies the probability of an entity spawning, the minimum and maximum count, and the entity's file path.

### `g_small_enemies`

This table lists various smaller enemy types that can appear in the Vault Frozen biome.

| Probability | Min Count | Max Count | Entity Path                                     | Notes                               |
| :---------- | :-------- | :-------- | :---------------------------------------------- | :---------------------------------- |
| `0.8`       | `0`       | `0`       | `""`                                            | Represents air, no spawn.           |
| `0.4`       | `1`       | `2`       | `data/entities/animals/vault/drone_physics.xml` |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/lasershooter.xml`  |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/roboguard.xml`     |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/assassin.xml`      |                                     |
| `0.3`       | `1`       | `1`       | `data/entities/animals/vault/acidshooter.xml`  |                                     |
| `0.18`      | `3`       | `5`       | `data/entities/animals/vault/blob.xml`          |                                     |
| `0.3`       | `1`       | `2`       | `data/entities/animals/vault/bigzombie.xml`     |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/scavenger_mine.xml`|                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/scavenger_invis.xml`     |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/icer.xml`          |                                     |
| `0.08`      | `1`       | `1`       | `data/entities/animals/icemage.xml`             |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/thunderskull.xml`  |                                     |
| `0.05`      | `1`       | `1`       | `data/entities/animals/scavenger_shield.xml`    |                                     |
| `0.002`     | `1`       | `1`       | `data/entities/animals/ultimate_killer.xml`     | Rare, powerful enemy.               |
| `0.07`      | `1`       | `1`       | `data/entities/animals/wizard_twitchy.xml`      |                                     |
| `0.07`      | `1`       | `1`       | `data/entities/animals/wizard_neutral.xml`      |                                     |
| `0.09`      | `1`       | `1`       | `data/entities/animals/drone_shield.xml`        |                                     |
| `0.1`       | `2`       | `4`       | `data/entities/animals/vault/scavenger_glue.xml`|                                     |
| `0.1`       | `1`       | `1`       | (Multiple entities)                             | Spawns one from a group of scavengers. |

### `g_big_enemies`

This table defines the larger and more formidable enemy types found in the Vault Frozen biome.

| Probability | Min Count | Max Count | Entity Path                                     | Notes                               |
| :---------- | :-------- | :-------- | :---------------------------------------------- | :---------------------------------- |
| `0.8`       | `0`       | `0`       | `""`                                            | Represents air, no spawn.           |
| `0.2`       | `1`       | `2`       | `data/entities/animals/vault/firemage.xml`      |                                     |
| `0.2`       | `1`       | `1`       | `data/entities/animals/vault/thundermage.xml`   |                                     |
| `0.04`      | `1`       | `1`       | `data/entities/animals/thundermage_big.xml`     |                                     |
| `0.1`       | `1`       | `1`       | (Multiple entities)                             | Spawns one from a group of robots.  |
| `0.2`       | `1`       | `2`       | (Multiple entities)                             | Spawns a group of scavengers.       |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/tank_rocket.xml`   |                                     |
| `0.05`      | `1`       | `1`       | `data/entities/animals/vault/tank_super.xml`    |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/scavenger_shield.xml`    |                                     |
| `0.2`       | `1`       | `1`       | `data/entities/animals/vault/missilecrab.xml`   |                                     |
| `0.1`       | `1`       | `1`       | `data/entities/animals/spearbot.xml`            |                                     |
| `0.07`      | `1`       | `1`       | `data/entities/animals/necrobot.xml`            |                                     |
| `0.01`      | `1`       | `1`       | `data/entities/animals/necrobot_super.xml`      | Rare, powerful necromancer.         |
| `0.03`      | `1`       | `1`       | `data/entities/animals/wizard_hearty.xml`       |                                     |
| `0.03`      | `1`       | `1`       | `data/entities/animals/wizard_weaken.xml`       |                                     |
| `0.05`      | `1`       | `1`       | (Multiple entities)                             | Spawns one from a group of icy/healers. |
| `0.05`      | `1`       | `1`       | (Multiple entities)                             | Spawns one from a group of missile/shields. |

## Environmental Elements

This section details the various environmental props and decorative elements that can be found within the Vault Frozen biome.

### `g_lamp`

Defines the types of lamps that can spawn.

| Probability | Min Count | Max Count | Offset Y | Entity Path                               |
| :---------- | :-------- | :-------- | :------- | :---------------------------------------- |
| `0.4`       | `1`       | `1`       | `0`      | `""`                                      |
| `1.0`       | `1`       | `1`       | `0`      | `data/entities/props/physics_tubelamp.xml`|
| `0.1`       | `1`       | `1`       | `-4`     | `data/entities/props/dripping_water.xml`  |
| `0.02`      | `1`       | `1`       | `-4`     | `data/entities/props/dripping_water_heavy.xml` |
| `0.1`       | `1`       | `1`       | `-4`     | `data/entities/props/dripping_oil.xml`    |
| `0.1`       | `1`       | `1`       | `-4`     | `data/entities/props/dripping_radioactive.xml` |

### `g_pipes_hor`, `g_pipes_ver`, `g_pipes_turn_right`, `g_pipes_turn_left`, `g_pipes_cross`

These tables define the different segments of pipe structures that can appear.

| Probability | Material File                               | Visual File                                   | Background File | Is Unique |
| :---------- | :------------------------------------------ | :-------------------------------------------- | :-------------- | :-------- |
| `0.5`       | `data/biome_impl/vault/pipe_hor_1.png`      | `data/biome_impl/vault/pipe_hor_1_visual.png` | `""`            | `0`       |
| `0.5`       | `data/biome_impl/vault/pipe_hor_2.png`      | `data/biome_impl/vault/pipe_hor_2_visual.png` | `""`            | `0`       |
| ...         | *(Similar entries for vertical, turns, cross)* |                                               |                 |           |

### `g_props`

This table lists various physics-enabled props that can spawn.

| Probability | Min Count | Max Count | Entity Path                               |
| :---------- | :-------- | :-------- | :---------------------------------------- |
| `0.2`       | `0`       | `0`       | `""`                                      |
| `0.1`       | `1`       | `1`       | `data/entities/props/physics_box_explosive.xml` |
| `0.1`       | `1`       | `1`       | `data/entities/props/physics_barrel_radioactive.xml` |
| `0.1`       | `1`       | `1`       | `data/entities/props/physics_barrel_oil.xml` |
| `0.2`       | `1`       | `1`       | `data/entities/props/physics_pressure_tank.xml` |
| `0.6`       | `1`       | `1`       | `data/entities/props/physics_propane_tank.xml` |

### `g_machines`

Defines the types of machines that can be found in the biome.

| Probability | Min Count | Max Count | Entity Path                           |
| :---------- | :-------- | :-------- | :------------------------------------ |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_1.xml` |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_2.xml` |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_3.xml` |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_4.xml` |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_5.xml` |
| `0.4`       | `1`       | `1`       | `data/entities/props/vault_machine_6.xml` |
| `1.4`       | `1`       | `1`       | `""`                                  |

### `g_barricade`

Specifies the type of barricade that can spawn.

| Probability | Min Count | Max Count | Entity Path                           |
| :---------- | :-------- | :-------- | :------------------------------------ |
| `1.0`       | `1`       | `1`       | `data/entities/props/physics_box_harmless.xml` |

## Item Spawning

The `g_items` table dictates the types of items that can be found, primarily wands.

### `g_items`

| Probability | Min Count | Max Count | Entity Path                     |
| :---------- | :-------- | :-------- | :------------------------------ |
| `0`         | `0`       | `0`       | `""`                            |
| `5`         | `1`       | `1`       | `data/entities/items/wand_level_05.xml` |
| `3`         | `1`       | `1`       | `data/entities/items/wand_unshuffle_03.xml` |
| `2`         | `1`       | `1`       | `data/entities/items/wand_unshuffle_04.xml` |

## Other Spawnable Elements

### `g_turret`

Defines the types of turrets that can spawn.

| Probability | Min Count | Max Count | Entity Path                     |
| :---------- | :-------- | :-------- | :------------------------------ |
| `0.5`       | `0`       | `0`       | `""`                            |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/turret_right.xml` |
| `0.1`       | `1`       | `1`       | `data/entities/animals/vault/turret_left.xml` |

### `g_candles`

Lists the different candle variants.

| Probability | Min Count | Max Count | Entity Path                     |
| :---------- | :-------- | :-------- | :------------------------------ |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_1.xml` |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_2.xml` |
| `0.33`      | `1`       | `1`       | `data/entities/props/physics_candle_3.xml` |

### `g_vines`

Specifies the types of vine structures.

| Probability | Min Count | Max Count | Entity Path                                       |
| :---------- | :-------- | :-------- | :------------------------------------------------ |
| `0.4`       | `1`       | `1`       | `data/entities/verlet_chains/cords/verlet_cord.xml` |
| `0.3`       | `1`       | `1`       | `data/entities/verlet_chains/cords/verlet_cord_long.xml` |
| `1.5`       | `1`       | `1`       | `""`                                              |
| `0.5`       | `1`       | `1`       | `data/entities/verlet_chains/cords/verlet_cord_short.xml` |
| `0.5`       | `1`       | `1`       | `data/entities/verlet_chains/cords/verlet_cord_shorter.xml` |
| `0.5`       | `1`       | `1`       | `data/entities/verlet_chains/slime_vine/slime_vine_short.xml` |
| `0.5`       | `1`       | `1`       | `data/entities/verlet_chains/slime_vine/slime_vine.xml` |

### `g_ghostlamp`

Defines the ghostly lamp variant.

| Probability | Min Count | Max Count | Offset Y | Entity Path                                   |
| :---------- | :-------- | :-------- | :------- | :-------------------------------------------- |
| `1.0`       | `1`       | `1`       | `10`     | `data/entities/props/physics_chain_torch_ghostly.xml` |

## Safety Zone

The `safe(x, y)` function defines a specific rectangular area within the biome where certain spawns are prevented.

*   **Area:** `x` between 125 and 249, `y` between 8694 and 8860.
*   **Effect:** If coordinates fall within this range, `safe` returns `false`, preventing spawns from tables that check this condition.

## Helper Functions

*   `spawn(table, x, y, ...)`: A general function to spawn entities from a given table at specified coordinates.
*   `load_pixel_scene(path, visual_path, x, y, ...)`: Loads a pre-defined pixel scene.
*   `EntityLoad(path, x, y)`: Loads a specific entity.
*   `ProceduralRandom(x, y)`: Generates a pseudo-random number based on coordinates.
*   `load_random_pixel_scene(table, x, y)`: Loads a pixel scene randomly selected from a table.