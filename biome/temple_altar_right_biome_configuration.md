---
title: Temple Altar Right Biome Configuration
category: biome
---

---

# Temple Altar Right Biome Configuration

This document details the configuration for the "Temple Altar Right" biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Functions

The `temple_altar_right.lua` script registers various functions to be called at specific points during biome generation and gameplay. These functions are triggered by unique hexadecimal identifiers.

### Registered Spawn Functions

| Identifier | Function Name        | Description                                     |
|------------|----------------------|-------------------------------------------------|
| `0xffffeedd` | `init`               | Initializes the biome and loads its visual assets. |
| `0xff6d934c` | `spawn_hp`           | Spawns health pickups.                          |
| `0xff33934c` | `spawn_shopitem`     | Spawns a standard shop item.                    |
| `0xff33935F` | `spawn_cheap_shopitem`| Spawns a cheaper shop item.                     |
| `0xff10822d` | `spawn_workshop`     | Spawns a workshop building.                     |
| `0xff5a822d` | `spawn_workshop_extra`| Spawns additional workshop elements.            |
| `0xffFAABBA` | `spawn_motordoor`    | Spawns a motor door.                            |
| `0xffFAABBB` | `spawn_pressureplate`| Spawns a pressure plate.                        |
| `0xffA85454` | `spawn_control_workshop`| Spawns workshop control elements.               |
| `0xff03DEAD` | `spawn_areachecks`   | Spawns area check entities.                     |
| `0xff7345DF` | `spawn_perk_reroll`  | Spawns a perk reroll item.                      |
| `0xffc128ff` | `spawn_rubble`       | Spawns rubble props.                            |
| `0xffa7a707` | `spawn_lamp_long`    | Spawns a long lamp.                             |
| `0xff9f2a00` | `spawn_statue`       | Spawns a temple statue.                         |

## Entity Spawning Configurations

### `g_lamp` Configuration

This table defines the properties for spawning lamps within the biome.

| Attribute   | Value                               | Description                                  |
|-------------|-------------------------------------|----------------------------------------------|
| `total_prob`| `0`                                 | Total probability for this group.            |
| `prob`      | `1.0`                               | Probability for the first entry (no entity). |
| `min_count` | `1`                                 | Minimum number of entities to spawn.         |
| `max_count` | `1`                                 | Maximum number of entities to spawn.         |
| `entity`    | `""`                                | No entity for the first entry.               |
| `prob`      | `1.0`                               | Probability for the second entry.            |
| `entity`    | `"data/entities/props/temple_lantern.xml"` | The entity to spawn (temple lantern).        |

### `g_rubble` Configuration

This table defines the properties for spawning rubble props.

| Attribute   | Value                                      | Description                                     |
|-------------|--------------------------------------------|-------------------------------------------------|
| `total_prob`| `0`                                        | Total probability for this group.               |
| `prob`      | `2.0`                                      | Probability for the first entry (no entity).    |
| `min_count` | `1`                                        | Minimum number of entities to spawn.            |
| `max_count` | `1`                                        | Maximum number of entities to spawn.            |
| `entity`    | `""`                                       | No entity for the first entry.                  |
| `prob`      | `0.1`                                      | Probability for subsequent entries.             |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Various rubble entities to spawn.               |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` |                                                 |
| `entity`    | `"data/entities/props/physics_temple_rubble_03.xml"` |                                                 |
| `entity`    | `"data/entities/props/physics_temple_rubble_04.xml"` |                                                 |
| `entity`    | `"data/entities/props/physics_temple_rubble_05.xml"` |                                                 |
| `entity`    | `"data/entities/props/physics_temple_rubble_06.xml"` |                                                 |

## Key Initialization and Spawning Functions

### `init(x, y, w, h)`

This function is called when the biome is initialized. It's responsible for setting up the core visual elements and structure of the "Temple Altar Right" biome.

*   Calls `spawn_altar_top(x, y, false)` to spawn the upper altar structure.
*   Loads pixel scene data for the biome's visual representation, including foreground, background, and extra elements.

### `spawn_hp(x, y)`

Spawns health-related pickups at the given coordinates.

*   `EntityLoad("data/entities/items/pickup/heart_fullhp_temple.xml", x-16, y)`: Spawns a full health pickup.
*   `EntityLoad("data/entities/items/pickup/heart_refresh.xml", x+16, y)`: Spawns a health refresh pickup.

### `spawn_shopitem(x, y)` and `spawn_cheap_shopitem(x, y)`

These functions handle the spawning of shop items.

*   `spawn_shopitem`: Calls `generate_shop_item(x, y, false)` to spawn a standard shop item.
*   `spawn_cheap_shopitem`: Calls `generate_shop_item(x, y, true)` to spawn a cheaper shop item.

### `spawn_workshop(x, y)` and `spawn_workshop_extra(x, y)`

These functions are responsible for placing workshop buildings.

*   `spawn_workshop`: Loads `workshop.xml` and `workshop_show_hint.xml`.
*   `spawn_workshop_extra`: Loads `workshop_allow_mods.xml`.

### `spawn_areachecks(x, y)`

This function conditionally spawns various "area check" entities, likely used for game logic or triggering events within the biome. The spawning is controlled by the `temple_should_we_spawn_checkers(x, y)` function.

*   Spawns horizontal and vertical area check entities at specific offsets relative to the provided `x` and `y` coordinates.

### `spawn_rubble(x, y)`

Uses the `g_rubble` configuration to spawn rubble props at the given coordinates.

### `spawn_statue(x, y)`

Spawns a temple statue entity at the specified location.

*   `EntityLoad("data/entities/props/temple_statue_02.xml", x, y)`

## Unused or Placeholder Functions

The following functions are defined but do not contain any implementation in this script, indicating they are either placeholders or their logic is handled elsewhere.

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
*   `spawn_wands(x, y)`