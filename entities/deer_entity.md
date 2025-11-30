---
title: Deer Entity
category: entities
---

# Deer Entity

This document details the configuration for the Deer entity in Noita, focusing on its AI, physical attributes, and visual representation.

## Core Components

The Deer entity is built upon a `base_helpless_animal.xml` foundation, inheriting general animal behaviors.

### AnimalAIComponent

This component governs the deer's artificial intelligence and behavior.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `preferred_job`           | `Escaping` | The primary behavior the deer will attempt to perform.                      |
| `attack_melee_enabled`    | `0`     | Melee attacks are disabled for the deer.                                    |
| `attack_ranged_enabled`   | `0`     | Ranged attacks are disabled for the deer.                                   |
| `sense_creatures`         | `1`     | The deer can detect other creatures in its vicinity.                        |
| `creature_detection_range_x` | `128`   | Horizontal range for creature detection.                                    |
| `creature_detection_range_y` | `160`   | Vertical range for creature detection.                                      |
| `can_fly`                 | `0`     | The deer cannot fly.                                                        |

### DamageModelComponent

Defines the deer's health and how it reacts to damage.

| Attribute                   | Value   | Description                                                                 |
| :-------------------------- | :------ | :-------------------------------------------------------------------------- |
| `ragdoll_filenames_file`    | `data/ragdolls/deer/filenames.txt` | Specifies the files used for the deer's ragdoll physics upon death. |
| `fire_probability_of_ignition` | `0.05`  | The chance (5%) that the deer will ignite when exposed to fire.             |
| `hp`                        | `0.8`   | The deer's health points.                                                   |

### SpriteComponent

Controls the visual appearance and animations of the deer.

| Attribute       | Value                         | Description                                                                 |
| :-------------- | :---------------------------- | :-------------------------------------------------------------------------- |
| `image_file`    | `data/enemies_gfx/deer.xml`   | The XML file defining the deer's graphical assets and animations.           |
| `rect_animation` | `stand`                       | The default animation state when the deer is idle.                          |
| `offset_x`      | `15`                          | Horizontal offset for the sprite.                                           |
| `offset_y`      | `25`                          | Vertical offset for the sprite.                                             |

### CharacterPlatformingComponent

Manages the deer's movement capabilities.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `jump_velocity_y` | `-12` | The vertical velocity applied when the deer jumps.                          |
| `run_velocity`  | `30`  | The horizontal speed at which the deer runs.                                |

### HitboxComponent

Defines the collision area for the deer.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-6.5` | Minimum X-coordinate of the bounding box.                                   |
| `aabb_max_x`  | `6.5` | Maximum X-coordinate of the bounding box.                                   |
| `aabb_min_y`  | `-10` | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max_y`  | `3`   | Maximum Y-coordinate of the bounding box.                                   |

### CharacterDataComponent

Provides fundamental character data, including collision properties.

| Attribute           | Value | Description                                                                 |
| :------------------ | :---- | :-------------------------------------------------------------------------- |
| `collision_aabb_min_x` | `-4.6` | Minimum X-coordinate for character collision.                               |
| `collision_aabb_max_x` | `4.6` | Maximum X-coordinate for character collision.                               |
| `collision_aabb_min_y` | `-10` | Minimum Y-coordinate for character collision.                               |
| `collision_aabb_max_y` | `3`   | Maximum Y-coordinate for character collision.                               |
| `mass`              | `2.4` | The mass of the deer entity.                                                |

## Other Notable Components

*   **PathFindingGridMarkerComponent**: Assigns a flag (`24`) for pathfinding grid usage.
*   **GenomeDataComponent**:
    *   `herd_id`: `helpless` - Indicates it belongs to a "helpless" herd.
    *   `food_chain_rank`: `20` - Its position in the food chain.
    *   `is_predator`: `0` - It is not a predator.
*   **PathFindingComponent**:
    *   `can_swim_on_surface`: `1` - Can swim on the surface of water.
    *   `can_dive`: `1` - Can dive underwater.