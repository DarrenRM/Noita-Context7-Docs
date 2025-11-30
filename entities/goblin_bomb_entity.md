---
title: Goblin Bomb Entity
category: entities
---

# Goblin Bomb Entity

This document describes the `goblin_bomb.xml` entity, a type of enemy found in Noita. It's a variant of a goblin that attacks with a ranged projectile.

## Core Components

The Goblin Bomb entity inherits from `base_enemy_basic.xml` and includes several key components that define its behavior and appearance.

### AnimalAIComponent

This component governs the AI and combat behavior of the Goblin Bomb.

| Attribute                       | Description                                                                 |
| :------------------------------ | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault` - Standard AI behavior.                                        |
| `escape_if_damaged_probability` | `70` - 70% chance to attempt to flee when damaged.                          |
| `creature_detection_range_x`    | `400` - Horizontal range for detecting creatures.                           |
| `creature_detection_range_y`    | `400` - Vertical range for detecting creatures.                             |
| `creature_detection_angular_range_deg` | `60` - Angular detection cone for creatures.                                |
| `sense_creatures`               | `1` - Enables creature sensing.                                               |
| `attack_melee_enabled`          | `1` - Melee attacks are enabled.                                            |
| `attack_melee_action_frame`     | `2` - The frame at which the melee attack animation occurs.                 |
| `attack_melee_max_distance`     | `10` - Maximum distance for melee attacks.                                  |
| `attack_melee_damage_min`       | `0.4` - Minimum damage dealt by melee attacks.                              |
| `attack_melee_damage_max`       | `0.7` - Maximum damage dealt by melee attacks.                              |
| `attack_ranged_enabled`         | `1` - Ranged attacks are enabled.                                           |
| `attack_ranged_action_frame`    | `5` - The frame at which the ranged attack animation occurs.                |
| `attack_ranged_min_distance`    | `10` - Minimum distance for ranged attacks.                                 |
| `attack_ranged_max_distance`    | `150` - Maximum distance for ranged attacks.                                |
| `attack_ranged_entity_file`     | `data/entities/projectiles/glitter_bomb.xml` - The projectile fired.        |
| `attack_ranged_frames_between`  | `300` - Frames to wait between ranged attacks.                              |
| `aggressiveness_min`            | `1` - Minimum aggressiveness level.                                         |
| `aggressiveness_max`            | `80` - Maximum aggressiveness level.                                        |

### DamageModelComponent

Defines the health and damage-related properties.

| Attribute                 | Description                                     |
| :------------------------ | :---------------------------------------------- |
| `hp`                      | `1` - Hit points of the entity.                 |
| `materials_create_messages` | `1` - Creates messages when damaged.            |
| `ragdoll_filenames_file`  | `data/ragdolls/goblin_bomb/filenames.txt` - Ragdoll configuration. |
| `blood_spray_material`    | `blood` - Material used for blood spray.        |
| `blood_multiplier`        | `0.5` - Multiplier for blood spray amount.      |

### SpriteComponent

Determines the visual representation of the Goblin Bomb.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/goblin_bomb.xml` - Path to the sprite definition. |

### PathFindingComponent

Handles the entity's movement and pathfinding capabilities.

| Attribute                   | Description                               |
| :-------------------------- | :---------------------------------------- |
| `can_jump`                  | `1` - Can jump.                           |
| `jump_speed`                | `80` - Speed of jumping.                  |
| `initial_jump_max_distance_x` | `60` - Maximum horizontal jump distance.  |
| `initial_jump_max_distance_y` | `60` - Maximum vertical jump distance.    |

### CharacterPlatformingComponent

Defines movement parameters for platforming.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `jump_velocity_y` | `-12` - Vertical jump velocity.           |
| `run_velocity`    | `32` - Horizontal movement speed.         |

### HitboxComponent

Defines the collision area for interactions.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `aabb_min_x`  | `-4` - Minimum X coordinate of the bounding box. |
| `aabb_max_x`  | `4` - Maximum X coordinate of the bounding box.  |
| `aabb_min_y`  | `-10` - Minimum Y coordinate of the bounding box. |
| `aabb_max_y`  | `3` - Maximum Y coordinate of the bounding box.   |

### CharacterDataComponent

General character properties.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `mass`        | `1.9` - Mass of the character.            |

## Other Notable Components

### LightComponent

Adds a light source to the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `radius`  | `50` - Radius of the light.               |
| `offset_y`| `-8` - Vertical offset of the light.      |

### AudioComponent

Defines the sound events associated with the Goblin Bomb.

| Attribute   | Description                               |
| :---------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` - Audio bank file. |
| `event_root`| `animals/goblin` - Root event name for goblin sounds. |

### GameEffectComponent

Applies a game effect to the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE` - The applied effect. |
| `frames`  | `-1` - Effect duration (infinite).        |