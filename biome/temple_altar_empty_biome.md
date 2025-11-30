---
title: Temple Altar Empty Biome
category: biome
---

# Temple Altar Empty Biome

This document describes the `temple_altar_empty.lua` script, which defines the behavior and spawning logic for an empty altar biome in Noita. This biome serves as a foundational template for other temple-related biomes.

## Core Functionality

The script primarily handles the initialization and spawning of various elements within the biome. It relies on several helper scripts for common Noita functionalities.

### Key Dependencies

*   `data/scripts/director_helpers.lua`: Provides general director and biome management functions.
*   `data/scripts/biome_scripts.lua`: Contains functions for biome-specific logic.
*   `data/scripts/items/generate_shop_item.lua`: Used for generating shop items.
*   `data/scripts/lib/utilities.lua`: Offers utility functions.
*   `data/scripts/biomes/temple_shared.lua`: Contains shared logic for temple biomes.
*   `data/scripts/perks/perk.lua`: Handles perk-related logic.

## Spawn Functions

The script registers several spawn functions that are called at specific points during gameplay or level generation.

### Registered Spawn Functions

| Function Name             | Description                                      | Trigger ID (Hex) |
| :------------------------ | :----------------------------------------------- | :--------------- |
| `init`                    | Initializes the biome.                           | `0xffffeedd`     |
| `spawn_hp`                | Placeholder for HP spawning.                     | `0xff6d934c`     |
| `spawn_all_shopitems`     | Spawns all shop items.                           | `0xff33934c`     |
| `spawn_workshop`          | Spawns workshop elements.                        | `0xff10822d`     |
| `spawn_workshop_extra`    | Spawns additional workshop elements.             | `0xff5a822d`     |
| `spawn_motordoor`         | Spawns a motor door.                             | `0xffFAABBA`     |
| `spawn_pressureplate`     | Spawns a pressure plate.                         | `0xffFAABBB`     |
| `spawn_areachecks`        | Placeholder for area checks.                     | `0xff03DEAD`     |
| `spawn_fish`              | Spawns fish entities.                            | `0xff03deaf`     |
| `spawn_worm_deflector`    | Spawns a worm deflector.                         | `0xff784dd2`     |
| `spawn_perk_reroll`       | Spawns a perk reroll item.                       | `0xff7345DF`     |
| `spawn_trigger_check_stats` | Spawns a trigger for checking stats.             | `0xff420A3D`     |
| `spawn_trigger_check_stats_reference` | Spawns a reference for checking stats. | `0xff420a3f`     |
| `spawn_rubble`            | Spawns rubble props.                             | `0xffc128ff`     |
| `spawn_lamp_long`         | Spawns a long lamp.                              | `0xffa7a707`     |
| `spawn_spell_visualizer`  | Spawns a spell visualizer.                       | `0xff03fade`     |

## Entity Definitions

The script defines several tables that specify entities to be spawned, along with their probabilities and counts.

### `g_lamp` Table

Defines the properties for spawning lamps.

| Attribute   | Value                                     | Description                               |
| :---------- | :---------------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                       | Total probability (often unused in this format). |
| `prob`      | `1.0`                                     | Probability of spawning.                  |
| `min_count` | `1`                                       | Minimum number of entities to spawn.      |
| `max_count` | `1`                                       | Maximum number of entities to spawn.      |
| `entity`    | `""`                                      | Placeholder, likely for a default or no entity. |
| `entity`    | `"data/entities/props/physics/temple_lantern.xml"` | The specific entity to spawn (temple lantern). |

### `g_fish` Table

Defines the properties for spawning fish.

| Attribute   | Value                                | Description                               |
| :---------- | :----------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                  | Total probability.                        |
| `prob`      | `5.0`                                | Probability of spawning.                  |
| `min_count` | `1`                                  | Minimum number of entities to spawn.      |
| `max_count` | `1`                                  | Maximum number of entities to spawn.      |
| `entity`    | `""`                                 | Placeholder.                              |
| `entity`    | `"data/entities/animals/fish.xml"`   | The specific entity to spawn (fish).      |

### `g_rubble` Table

Defines the properties for spawning rubble.

| Attribute   | Value                                         | Description                               |
| :---------- | :-------------------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                           | Total probability.                        |
| `prob`      | `2.0`                                         | Probability of spawning.                  |
| `min_count` | `1`                                           | Minimum number of entities to spawn.      |
| `max_count` | `1`                                           | Maximum number of entities to spawn.      |
| `entity`    | `""`                                          | Placeholder.                              |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Specific rubble entity.                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` | Specific rubble entity.                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_03.xml"` | Specific rubble entity.                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_04.xml"` | Specific rubble entity.                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_05.xml"` | Specific rubble entity.                   |
| `entity`    | `"data/entities/props/physics_temple_rubble_06.xml"` | Specific rubble entity.                   |

## Key Functions

### `init(x, y, w, h)`

This is the primary initialization function for the biome.

*   Calls `temple_random(x, y)` for general temple initialization.
*   Sets a random seed based on the biome's coordinates.
*   Loads a background sprite: `data/biome_impl/temple/wall_background.png`.
*   Conditionally loads different `altar_top` pixel scenes based on a random number, introducing variations like water, blood, oil, radioactive, or lava tops.
*   Loads the main altar scene: `data/biome_impl/temple/altar_empty.png` with its visual and background components.

### `spawn_lamp(x, y)` and `spawn_lamp_long(x, y)`

These functions utilize the `g_lamp` table to spawn temple lanterns at the given coordinates. `spawn_lamp_long` allows for a slightly larger spawn range.

### `spawn_fish(x, y)`

Spawns fish entities using the `g_fish` table.

### `spawn_rubble(x, y)`

Spawns various rubble props defined in the `g_rubble` table.

### `spawn_worm_deflector(x, y)`

Spawns the components for a worm deflector, including crystal and base parts.

### `spawn_perk_reroll(x, y)`

Spawns a `perk_reroll` pickup item.

### `spawn_spell_visualizer(x, y)`

Spawns a spell visualizer and an AABB entity.

## Placeholder Functions

Several functions are defined but currently empty. These are likely intended for future implementation or are handled by other scripts.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`
*   `spawn_hp(x, y)`
*   `spawn_shopitem(x, y)`
*   `spawn_cheap_shopitem(x, y)`
*   `spawn_all_shopitems(x, y)`
*   `spawn_workshop(x, y)`
*   `spawn_areachecks(x, y)`
*   `spawn_all_perks(x, y)`
*   `spawn_trigger_check_stats(x, y)`
*   `spawn_trigger_check_stats_reference(x, y)`