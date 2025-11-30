---
title: Skullfly Entity Documentation
category: entities
---

# Skullfly Entity Documentation

This document details the `skullfly.xml` entity, providing key attributes for AI-assisted modding.

## Entity: Skullfly

The Skullfly is a flying enemy entity in Noita.

### Base Entity Configuration

The Skullfly inherits its core functionality from `data/entities/base_enemy_flying.xml`.

### Key Components and Attributes

#### AnimalAIComponent

Manages the AI behavior of the Skullfly.

| Attribute                      | Value                               | Description                                                                 |
| :----------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                     | `1`                                 | Enables the AI component.                                                   |
| `preferred_job`                | `JobDefault`                        | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability`| `50`                                | Percentage chance to flee when damaged.                                     |
| `attack_ranged_min_distance`   | `20`                                | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`   | `200`                               | Maximum distance for ranged attacks.                                        |
| `creature_detection_range_x`   | `300`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`   | `300`                               | Vertical range for detecting creatures.                                     |
| `attack_ranged_action_frame`   | `5`                                 | Frame within the attack animation when the ranged attack is performed.      |
| `attack_ranged_entity_file`    | `data/entities/projectiles/darkflame.xml` | The projectile entity spawned for ranged attacks.                           |
| `attack_ranged_frames_between` | `100`                               | Number of frames to wait between ranged attacks.                            |
| `sense_creatures`              | `1`                                 | Enables creature sensing.                                                   |
| `attack_ranged_enabled`        | `1`                                 | Enables ranged attacks.                                                     |
| `attack_melee_enabled`         | `1`                                 | Enables melee attacks.                                                      |
| `can_fly`                      | `1`                                 | Indicates the creature can fly.                                             |
| `food_material`                | `blood`                             | The material this creature consumes for food (though `needs_food` is 0).    |
| `needs_food`                   | `0`                                 | Whether the creature requires food to survive.                              |

#### DamageModelComponent

Defines the health and damage-related properties.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                      | `4.2`                               | Hit points of the Skullfly.                                                 |
| `ragdoll_material`        | `meat_slime_cursed`                 | Material used for the ragdoll when defeated.                                |
| `ragdoll_filenames_file`  | `data/ragdolls/skullfly/filenames.txt` | File listing the sprites for the ragdoll.                                   |
| `blood_material`          | `slime`                             | The material of the blood splatters.                                        |
| `blood_spray_material`    | `slime`                             | The material of the blood spray.                                            |
| `blood_multiplier`        | `0.2`                               | Multiplier for blood effects.                                               |
| `fire_probability_of_ignition` | `5`                                 | Percentage chance to ignite from fire.                                      |
| `air_lack_of_damage`      | `0.2`                               | Damage taken per second when lacking air.                                   |
| `air_needed`              | `1`                                 | Whether the creature requires air.                                          |
| `blood_sprite_directional`| `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` | Sprite for directional blood splatters.                                     |
| `blood_sprite_large`      | `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` | Sprite for large blood splatters.                                           |

##### Damage Multipliers

| Type  | Value | Description                                     |
| :---- | :---- | :---------------------------------------------- |
| `holy`| `1.2` | Multiplier for holy damage taken.               |

#### SpriteComponent

Defines the visual appearance of the Skullfly.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `image_file`| `data/enemies_gfx/skullfly.xml`     | The XML file defining the sprite animations.    |
| `offset_x`  | `0`                                 | Horizontal offset for the sprite.               |
| `offset_y`  | `0`                                 | Vertical offset for the sprite.                 |

#### PathFindingComponent

Controls the movement and pathfinding capabilities.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `can_fly` | `1`   | Indicates the creature can fly.                 |
| `can_walk`| `0`   | Indicates the creature cannot walk.             |

#### HitboxComponent

Defines the collision area of the Skullfly.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `aabb_max_x`| `7`   | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`| `1`   | Maximum Y-coordinate of the bounding box.       |
| `aabb_min_x`| `-7`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`| `-16` | Minimum Y-coordinate of the bounding box.       |

#### CharacterDataComponent

General character data, including collision bounds and mass.

| Attribute          | Value | Description                                     |
| :----------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x` | `-6`  | Minimum X-coordinate for collision.             |
| `collision_aabb_max_x` | `6`   | Maximum X-coordinate for collision.             |
| `collision_aabb_min_y` | `-6`  | Minimum Y-coordinate for collision.             |
| `collision_aabb_max_y` | `2`   | Maximum Y-coordinate for collision.             |
| `mass`             | `2.0` | Mass of the character.                          |

#### AudioComponent

Manages the sound effects for the Skullfly.

| Attribute   | Value                           | Description                                     |
| :---------- | :------------------------------ | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | The audio bank file containing the sounds.      |
| `event_root`| `animals/skullfly`              | The root event name for Skullfly sounds.        |