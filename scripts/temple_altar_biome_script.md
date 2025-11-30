---
title: Temple Altar Biome Script
category: scripts/
---

# Temple Altar Biome Script

This script defines the entities and behaviors associated with the Temple Altar biome in Noita. It handles the spawning of various elements, including shops, perks, and environmental props, based on specific trigger conditions and random probabilities.

## Core Functionality

The script registers several spawn functions that are called by the game's director system based on specific entity IDs or biome triggers. These functions are responsible for populating the biome with its unique content.

### Registered Spawn Functions

| Trigger ID | Function Name             | Description                                      |
| :--------- | :------------------------ | :----------------------------------------------- |
| `0xffffeedd` | `init`                    | Initializes the altar biome.                     |
| `0xff6d934c` | `spawn_hp`                | Spawns health pickups and related entities.      |
| `0xff33934c` | `spawn_all_shopitems`     | Spawns shop items and potentially wands.         |
| `0xff10822d` | `spawn_workshop`          | Spawns a standard workshop.                      |
| `0xff5a822d` | `spawn_workshop_extra`    | Spawns a workshop that allows mods.              |
| `0xffFAABBA` | `spawn_motordoor`         | Spawns a temple motor door.                      |
| `0xffFAABBB` | `spawn_pressureplate`     | Spawns a temple pressure plate.                  |
| `0xff03DEAD` | `spawn_areachecks`        | Spawns area check entities.                      |
| `0xff03deaf` | `spawn_fish`              | Spawns fish entities.                            |
| `0xff784dd2` | `spawn_worm_deflector`    | Spawns a worm deflector.                         |
| `0xff7345DF` | `spawn_perk_reroll`       | Spawns a perk reroll item.                       |
| `0xff420A3D` | `spawn_trigger_check_stats` | Spawns a trigger to check player stats.          |
| `0xff420a3f` | `spawn_trigger_check_stats_reference` | Spawns a reference for checking player stats. |
| `0xffc128ff` | `spawn_rubble`            | Spawns rubble props.                             |
| `0xffa7a707` | `spawn_lamp_long`         | Spawns a long temple lamp.                       |
| `0xff03fade` | `spawn_spell_visualizer`  | Spawns spell visualizer and AABB entities.       |

## Key Entity Spawning Functions

### `init(x, y, w, h)`

This function is called upon initialization of the altar biome. It loads the primary altar visual elements and background.

*   Loads `data/biome_impl/temple/altar.png` and `data/biome_impl/temple/altar_visual.png`.
*   Loads `data/biome_impl/temple/altar_background.png`.
*   Calls `spawn_altar_top(x, y, false)` to place the altar structure.

### `spawn_hp(x, y)`

Handles the spawning of health-related items and other utility entities.

*   Spawns `data/entities/items/pickup/heart_fullhp_temple.xml`.
*   Spawns `data/entities/buildings/music_trigger_temple.xml`.
*   Spawns `data/entities/items/pickup/spell_refresh.xml`.
*   Spawns `data/entities/buildings/coop_respawn.xml`.

### `spawn_all_shopitems(x, y)`

This function is responsible for generating the shop content within the altar biome. It can spawn either items or wands, with a chance for a sale item.

*   Determines whether to spawn shop items or wands based on `temple_random(x, y)`.
*   Spawns `data/entities/buildings/shop_hitbox.xml`.
*   Sets a random seed for item generation.
*   Spawns a configurable number of shop items or wands using `generate_shop_item` or `generate_shop_wand`.
*   Has a 50% chance to spawn a second row of items.
*   Loads `data/biome_impl/temple/shop_second_row.png` for the second row visuals.

### `spawn_rubble(x, y)`

Spawns various rubble props within the biome.

*   Uses the `g_rubble` table to define probabilities and entities for different rubble types.
*   Includes entities like `data/entities/props/physics_temple_rubble_01.xml` through `06.xml`.

### `spawn_fish(x, y)`

Spawns fish entities, with the number of fish potentially scaling with the player's total orb count.

*   Iterates based on `GameGetOrbCountAllTime()`.
*   Spawns `data/entities/animals/fish.xml`.

## Configuration Tables

### `g_lamp`

Defines the entities and probabilities for spawning lamps.

| Prob | Min Count | Max Count | Entity                                    |
| :--- | :-------- | :-------- | :---------------------------------------- |
| 1.0  | 1         | 1         | "" (empty, likely for default behavior)   |
| 1.0  | 1         | 1         | `data/entities/props/physics/temple_lantern.xml` |

### `g_fish`

Defines the entities and probabilities for spawning fish.

| Prob | Min Count | Max Count | Entity                   |
| :--- | :-------- | :-------- | :----------------------- |
| 5.0  | 1         | 1         | "" (empty)               |
| 1.0  | 2         | 5         | `data/entities/animals/fish.xml` |

### `g_rubble`

Defines the entities and probabilities for spawning rubble.

| Prob | Min Count | Max Count | Entity                                         |
| :--- | :-------- | :-------- | :--------------------------------------------- |
| 2.0  | 1         | 1         | "" (empty)                                     |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_01.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_02.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_03.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_04.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_05.xml` |
| 0.1  | 1         | 1         | `data/entities/props/physics_temple_rubble_06.xml` |

## Unused/Commented Functions

Several functions are defined but commented out or have empty implementations, indicating they are either deprecated, not currently used, or intended for future development.

*   `spawn_small_enemies`, `spawn_big_enemies`, `spawn_items`, `spawn_props`, `spawn_props2`, `spawn_props3`
*   `load_pixel_scene`, `load_pixel_scene2`
*   `spawn_unique_enemy`, `spawn_unique_enemy2`, `spawn_unique_enemy3`
*   `spawn_ghostlamp`, `spawn_candles`, `spawn_potions`
*   `spawn_shopitem`, `spawn_cheap_shopitem` (commented out, replaced by `spawn_all_shopitems`)