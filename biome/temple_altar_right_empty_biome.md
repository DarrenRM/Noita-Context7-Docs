---
title: Temple Altar Right Empty Biome
category: biome
---

---

# Temple Altar Right Empty Biome

This document describes the configuration for the `temple_altar_right_empty.lua` biome script in Noita, focusing on its entity spawning and visual setup.

## Core Functionality

This script defines a specific biome layout within the Temple area, characterized by an empty altar structure on the right side. It leverages several helper functions and registers various spawn points for different game elements.

## Key Spawn Functions

The script registers multiple spawn functions, triggered by specific entity IDs. These functions dictate what entities or visual elements appear at designated locations within the biome.

### Registered Spawn Functions:

| Trigger ID | Function Name        | Description                                     |
|------------|----------------------|-------------------------------------------------|
| `0xffffeedd` | `init`               | Initializes the biome's core visual elements.   |
| `0xff6d934c` | `spawn_hp`           | Placeholder for HP spawning (currently empty).  |
| `0xff33934c` | `spawn_shopitem`     | Placeholder for shop item spawning (currently empty). |
| `0xff33935F` | `spawn_cheap_shopitem` | Placeholder for cheap shop item spawning (currently empty). |
| `0xff10822d` | `spawn_workshop`     | Placeholder for workshop spawning (currently empty). |
| `0xff5a822d` | `spawn_workshop_extra` | Placeholder for extra workshop spawning (currently empty). |
| `0xffFAABBA` | `spawn_motordoor`    | Placeholder for motor door spawning (currently empty). |
| `0xffFAABBB` | `spawn_pressureplate`| Placeholder for pressure plate spawning (currently empty). |
| `0xffA85454` | `spawn_control_workshop` | Placeholder for control workshop spawning (currently empty). |
| `0xff03DEAD` | `spawn_areachecks`   | Placeholder for area check spawning (currently empty). |
| `0xff7345DF` | `spawn_perk_reroll`  | Placeholder for perk reroll spawning (currently empty). |
| `0xffc128ff` | `spawn_rubble`       | Spawns rubble props.                            |
| `0xffa7a707` | `spawn_lamp_long`    | Spawns long temple lamps.                       |
| `0xff9f2a00` | `spawn_statue`       | Spawns a temple statue.                         |

## Visual Elements (`init` function)

The `init` function is responsible for loading the primary visual components of this biome.

### Key Visual Loading:

*   **Background:** `LoadBackgroundSprite("data/biome_impl/temple/wall_background.png", x, y - 30, 35)` loads the main background sprite.
*   **Altar Top:** `LoadPixelScene( "data/biome_impl/temple/altar_top.png", "", x, y-40, "", true )` loads the top part of the altar.
*   **Altar Right:** `LoadPixelScene( "data/biome_impl/temple/altar_right.png", "data/biome_impl/temple/altar_right_visual.png", x, y-40+300, "data/biome_impl/temple/altar_right_background.png", true )` loads the main right altar structure and its associated visual and background layers.
*   **Altar Right Extra:** `LoadPixelScene( "data/biome_impl/temple/altar_right_extra.png", "", x, y-40+300+282, "", true )` loads additional elements for the right altar.
*   **Workshop Collapse:** `EntityLoad("data/entities/misc/workshop_collapse.xml", x+28, y+54-40+300)` places a "workshop collapse" entity.

## Prop Definitions

The script defines tables for spawning specific props, primarily lamps and rubble.

### `g_lamp` Table:

This table defines the probability and entity for spawning lamps.

| Attribute   | Value                                | Description                               |
|-------------|--------------------------------------|-------------------------------------------|
| `total_prob`| `0`                                  | Total probability (not actively used here). |
| `prob`      | `1.0`                                | Probability of spawning.                  |
| `min_count` | `1`                                  | Minimum number of entities to spawn.      |
| `max_count` | `1`                                  | Maximum number of entities to spawn.      |
| `entity`    | `""`                                 | Empty entity (likely a placeholder).      |
| `entity`    | `"data/entities/props/physics/temple_lantern.xml"` | The entity to spawn (temple lantern).     |

### `g_rubble` Table:

This table defines the probability and entities for spawning various rubble props.

| Attribute   | Value                                | Description                               |
|-------------|--------------------------------------|-------------------------------------------|
| `total_prob`| `0`                                  | Total probability (not actively used here). |
| `prob`      | `2.0`                                | Base probability for rubble.              |
| `min_count` | `1`                                  | Minimum number of entities to spawn.      |
| `max_count` | `1`                                  | Maximum number of entities to spawn.      |
| `entity`    | `""`                                 | Empty entity (likely a placeholder).      |
| `prob`      | `0.1`                                | Probability for specific rubble types.    |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Rubble prop 01.                           |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` | Rubble prop 02.                           |
| `entity`    | `"data/entities/props/physics_temple_rubble_03.xml"` | Rubble prop 03.                           |
| `entity`    | `"data/entities/props/physics_temple_rubble_04.xml"` | Rubble prop 04.                           |
| `entity`    | `"data/entities/props/physics_temple_rubble_05.xml"` | Rubble prop 05.                           |
| `entity`    | `"data/entities/props/physics_temple_rubble_06.xml"` | Rubble prop 06.                           |

## Unused/Placeholder Functions

Several functions are defined but currently contain no implementation (`end`). These are likely intended for future expansion or are part of a generic biome template.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_hp`
*   `spawn_shopitem`
*   `spawn_cheap_shopitem`
*   `spawn_workshop`
*   `spawn_workshop_extra`
*   `spawn_motordoor`
*   `spawn_pressureplate`
*   `spawn_control_workshop`
*   `spawn_perk_reroll`
*   `spawn_areachecks`
*   `spawn_wands`