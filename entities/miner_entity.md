---
title: Miner Entity
category: entities
---

# Miner Entity

This document details the configuration of the Miner entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Attributes

The Miner is a basic enemy with melee and ranged attack capabilities, a preference for food, and the ability to detect creatures.

### AnimalAIComponent

This component governs the Miner's behavior and combat.

| Attribute                       | Value                                     | Description                                                                 |
| :------------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                      | `1`                                       | Enables the AI component.                                                   |
| `preferred_job`                 | `JobDefault`                              | The default job assigned to this entity.                                    |
| `escape_if_damaged_probability` | `40`                                      | Percentage chance to flee when damaged.                                     |
| `attack_melee_damage_min`       | `0.4`                                     | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`       | `0.7`                                     | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`    | `300`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `300`                                     | Vertical range for detecting creatures.                                     |
| `food_material`                 | `meat`                                    | The material considered as food for this creature.                          |
| `needs_food`                    | `1`                                       | Whether the creature requires food to survive.                              |
| `sense_creatures`               | `1`                                       | Whether the creature can sense other creatures.                             |
| `attack_ranged_enabled`         | `1`                                       | Enables ranged attacks.                                                     |
| `attack_melee_enabled`          | `1`                                       | Enables melee attacks.                                                      |
| `attack_ranged_entity_file`     | `data/entities/projectiles/tnt.xml`       | The entity file used for ranged attacks (TNT in this case).               |
| `attack_ranged_frames_between`  | `100`                                     | Number of frames between ranged attacks.                                    |

### DamageModelComponent

Defines the Miner's health and how it reacts to damage.

| Attribute                     | Value                               | Description                                                              |
| :---------------------------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `hp`                          | `1.0`                               | Hit points of the Miner.                                                 |
| `materials_create_messages`   | `1`                                 | Whether damage materials create messages.                                |
| `ragdoll_filenames_file`      | `data/ragdolls/miner/filenames.txt` | File containing filenames for the Miner's ragdoll.                       |
| `fire_probability_of_ignition`| `5`                                 | Percentage chance of igniting from fire.                                 |
| `blood_spray_material`        | `blood`                             | The material used for blood spray.                                       |
| `blood_spray_create_some_cosmetic` | `1`                                 | Whether to create some cosmetic blood spray effects.                     |

#### damage_multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `explosion` | `0.2`      |

### SpriteComponent

Controls the visual representation of the Miner.

| Attribute   | Value                         | Description                               |
| :---------- | :---------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/miner.xml`  | The sprite image file for the Miner.      |
| `offset_x`  | `0`                           | Horizontal offset of the sprite.          |
| `offset_y`  | `0`                           | Vertical offset of the sprite.            |

### PathFindingComponent

Defines the Miner's movement capabilities.

| Attribute                  | Value | Description                                     |
| :------------------------- | :---- | :---------------------------------------------- |
| `can_jump`                 | `1`   | Whether the Miner can jump.                     |
| `can_fly`                  | `0`   | Whether the Miner can fly.                      |
| `jump_speed`               | `100` | The speed at which the Miner jumps.             |
| `initial_jump_lob`         | `1`   | The initial upward force of a jump.             |
| `initial_jump_max_distance_x` | `60`  | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y` | `60`  | Maximum vertical distance of a jump.            |
| `can_swim_on_surface`      | `1`   | Whether the Miner can swim on the surface.      |
| `can_dive`                 | `1`   | Whether the Miner can dive.                     |

### CharacterPlatformingComponent

Governs the Miner's ground-based movement.

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `jump_velocity_y` | `-12` | The vertical velocity applied when jumping. |
| `run_velocity`| `12`  | The horizontal movement speed.            |

### HitboxComponent

Defines the collision areas for the Miner.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-3`  | Minimum X-axis bounding box coordinate.   |
| `aabb_max_x`| `3`   | Maximum X-axis bounding box coordinate.   |
| `aabb_min_y`| `-6`  | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_y`| `3`   | Maximum Y-axis bounding box coordinate.   |

## Other Notable Components

### LightComponent

The Miner emits a light source.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `radius`    | `50`  | The radius of the light.                  |
| `fade_out_time` | `1.5` | The time it takes for the light to fade out. |

### AudioComponent

Manages the sound effects for the Miner.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | The audio bank file.                      |
| `event_root`| `animals/miner`                     | The root event name for Miner sounds.     |

### GameEffectComponent

Applies a specific game effect to the Miner.

| Attribute | Value             | Description                               |
| :-------- | :---------------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE` | The game effect applied (radioactive allergy). |
| `frames`  | `-1`              | Duration of the effect (-1 means infinite). |