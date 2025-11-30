---
title: Shotgunner Enemy Entity
category: entities
---

# Shotgunner Enemy Entity

This document details the `shotgunner.xml` entity file, which defines the behavior and attributes of the Shotgunner enemy in Noita.

## Core Attributes

The Shotgunner is a basic enemy with ranged attack capabilities, utilizing a buckshot projectile.

### `AnimalAIComponent`

This component governs the AI behavior of the Shotgunner.

| Attribute                      | Description                                                                 |
| :----------------------------- | :-------------------------------------------------------------------------- |
| `escape_if_damaged_probability`| Probability (0-100) of escaping when damaged.                               |
| `attack_melee_damage_min`      | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`      | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`   | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`   | Vertical range for detecting creatures.                                     |
| `creature_detection_angular_range_deg` | Angular range (degrees) for creature detection.                             |
| `attack_melee_max_distance`    | Maximum distance for melee attacks.                                         |
| `food_material`                | Material the creature considers food.                                       |
| `needs_food`                   | Whether the creature requires food to survive.                              |
| `sense_creatures`              | Whether the creature can sense other creatures.                             |
| `attack_ranged_enabled`        | Enables ranged attacks.                                                     |
| `attack_melee_enabled`         | Enables melee attacks.                                                      |
| `attack_ranged_entity_file`    | Path to the projectile entity file for ranged attacks (e.g., `buckshot.xml`). |
| `attack_ranged_entity_count_min` | Minimum number of projectiles fired per ranged attack.                      |
| `attack_ranged_entity_count_max` | Maximum number of projectiles fired per ranged attack.                      |
| `attack_ranged_frames_between` | Frames to wait between ranged attacks.                                      |
| `attack_ranged_offset_y`       | Vertical offset for the origin of ranged attacks.                           |

### `DamageModelComponent`

Defines the health and damage-related properties of the Shotgunner.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `hp`                          | Hit points of the entity.                                                |
| `materials_create_messages`   | Whether materials on the entity create messages when damaged.            |
| `ragdoll_filenames_file`      | Path to the file defining ragdoll sprites.                               |
| `fire_probability_of_ignition`| Probability (0-100) of igniting from fire.                               |
| `blood_spray_material`        | Material used for blood spray effects.                                   |
| `blood_spray_create_some_cosmetic` | Whether to create cosmetic blood spray effects.                          |

### `SpriteComponent`

Determines the visual appearance of the Shotgunner.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `image_file`| Path to the sprite definition file.       |
| `offset_x`  | Horizontal offset of the sprite.          |
| `offset_y`  | Vertical offset of the sprite.            |

### `PathFindingComponent`

Controls the Shotgunner's movement and pathfinding capabilities.

| Attribute                   | Description                                                              |
| :-------------------------- | :----------------------------------------------------------------------- |
| `can_jump`                  | Whether the entity can jump.                                             |
| `can_fly`                   | Whether the entity can fly.                                              |
| `jump_speed`                | The speed at which the entity jumps.                                     |
| `initial_jump_lob`          | Controls the arc of a jump.                                              |
| `initial_jump_max_distance_x`| Maximum horizontal distance the entity can jump.                         |
| `initial_jump_max_distance_y`| Maximum vertical distance the entity can jump.                           |
| `can_swim_on_surface`       | Whether the entity can swim on the surface of liquids.                   |
| `can_dive`                  | Whether the entity can dive underwater.                                  |

### `CharacterPlatformingComponent`

Defines movement parameters for platforming.

| Attribute      | Description                               |
| :------------- | :---------------------------------------- |
| `jump_velocity_y`| Initial vertical velocity when jumping.   |
| `run_velocity` | Horizontal movement speed.                |

### `CharacterDataComponent`

General character data, including collision and mass.

| Attribute           | Description                               |
| :------------------ | :---------------------------------------- |
| `collision_aabb_min_x`| Minimum X-coordinate of the collision box. |
| `collision_aabb_max_x`| Maximum X-coordinate of the collision box. |
| `collision_aabb_min_y`| Minimum Y-coordinate of the collision box. |
| `collision_aabb_max_y`| Maximum Y-coordinate of the collision box. |
| `mass`              | The mass of the entity.                   |

## Other Notable Components

### `ItemChestComponent`

Indicates that the entity can contain items, with a specified loot level.

### `GenomeDataComponent`

Provides genetic information, including herd ID, food chain rank, and predator status.

### `CameraBoundComponent`

Manages how the entity interacts with the camera's bounds.

### `HitboxComponent`

Defines the entity's hitbox for damage and interaction. The second `HitboxComponent` has a `damage_multiplier` of 2.5, suggesting it's a critical hit area.

### `LightComponent`

Adds a light source to the entity with specified radius and fade-out time.

### `AudioComponent`

Specifies the audio bank and event root for the entity's sounds.

### `Entity` with `GameEffectComponent`

This nested entity applies a permanent radioactive allergy effect to the Shotgunner.

### `HotspotComponent`

Defines a "hand" hotspot for potential interactions.