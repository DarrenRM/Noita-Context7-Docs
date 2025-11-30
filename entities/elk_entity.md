---
title: Elk Entity
category: entities
---

# Elk Entity

This document describes the `elk.xml` entity, a passive creature in Noita.

## Core Attributes

The Elk is a `mortal` and `prey` entity, meaning it can be killed and is a food source for predators.

## Base Entity Configuration

The Elk inherits its core functionality from `data/entities/base_helpless_animal.xml`.

### AnimalAIComponent

This component governs the Elk's behavior.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `preferred_job`           | `Escaping` | The Elk's primary AI directive is to flee from danger.                      |
| `attack_melee_enabled`    | `0`     | The Elk cannot perform melee attacks.                                       |
| `attack_ranged_enabled`   | `0`     | The Elk cannot perform ranged attacks.                                      |
| `sense_creatures`         | `1`     | The Elk can detect other creatures in its vicinity.                         |
| `creature_detection_range_x` | `128`   | The horizontal range at which the Elk can detect creatures.                 |
| `creature_detection_range_y` | `160`   | The vertical range at which the Elk can detect creatures.                   |

### DamageModelComponent

Defines the Elk's health and how it reacts to damage.

| Attribute                   | Value   | Description                                                                 |
| :-------------------------- | :------ | :-------------------------------------------------------------------------- |
| `ragdoll_filenames_file`    | `data/ragdolls/elk/filenames.txt` | Specifies the files used for the Elk's ragdoll physics upon death. |
| `fire_probability_of_ignition` | `0.05`  | The chance (5%) that the Elk will ignite when taking damage.                |
| `hp`                        | `1.0`   | The Elk's health points.                                                    |

### SpriteComponent

Controls the visual representation of the Elk.

| Attribute         | Value                           | Description                                                                 |
| :---------------- | :------------------------------ | :-------------------------------------------------------------------------- |
| `image_file`      | `data/enemies_gfx/elk.xml`      | The XML file defining the Elk's graphical assets and animations.            |
| `offset_x`        | `15`                            | Horizontal offset for the sprite.                                           |
| `offset_y`        | `27`                            | Vertical offset for the sprite.                                             |
| `rect_animation`  | `stand`                         | The default animation played when the Elk is idle.                          |

### CharacterPlatformingComponent

Manages the Elk's movement capabilities.

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `jump_velocity_y` | `-12`   | The vertical velocity applied when the Elk jumps.                           |
| `run_velocity`  | `12`    | The horizontal speed at which the Elk runs.                                 |

### HitboxComponent

Defines the collision area for the Elk.

| Attribute     | Value   | Description                                                                 |
| :------------ | :------ | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-8.5`  | Minimum X-coordinate of the bounding box.                                   |
| `aabb_max_x`  | `8.5`   | Maximum X-coordinate of the bounding box.                                   |
| `aabb_min_y`  | `-10`   | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max_y`  | `5`     | Maximum Y-coordinate of the bounding box.                                   |

### CharacterDataComponent

Provides general character data, including collision and mass.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `collision_aabb_min_x` | `-5.6`  | Minimum X-coordinate for collision detection.                               |
| `collision_aabb_max_x` | `5.6`   | Maximum X-coordinate for collision detection.                               |
| `collision_aabb_min_y` | `-10`   | Minimum Y-coordinate for collision detection.                               |
| `collision_aabb_max_y` | `3`     | Maximum Y-coordinate for collision detection.                               |
| `mass`                | `2.7`   | The mass of the Elk, affecting physics interactions.                        |

### GenomeDataComponent

Contains genetic information relevant to the game's ecosystem.

| Attribute         | Value   | Description                                                                 |
| :---------------- | :------ | :-------------------------------------------------------------------------- |
| `herd_id`         | `helpless` | Identifies the herd or group the Elk belongs to.                            |
| `food_chain_rank` | `20`    | Its position in the food chain (higher means higher trophic level).         |
| `is_predator`     | `0`     | Indicates that the Elk is not a predator.                                   |