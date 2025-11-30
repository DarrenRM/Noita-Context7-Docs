---
title: Sniper Enemy Entity
category: entities
---

# Sniper Enemy Entity

This document details the configuration for the "Sniper" enemy entity in Noita, focusing on its AI, combat capabilities, and physical attributes.

## Core Components

### `Base` Entity Configuration

The Sniper inherits its fundamental properties from `base_enemy_basic.xml`.

### `AnimalAIComponent`

This component governs the Sniper's behavior, including its detection, aggression, and attack patterns.

| Attribute                       | Value                                     | Description                                                                 |
| :------------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault`                              | Default job assigned to the AI.                                             |
| `escape_if_damaged_probability` | `70`                                      | Percentage chance to flee when damaged.                                     |
| `creature_detection_range_x`    | `700`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `700`                                     | Vertical range for detecting creatures.                                     |
| `sense_creatures`               | `1`                                       | Enables creature sensing.                                                   |
| `aggressiveness_min`            | `80`                                      | Minimum aggressiveness level.                                               |
| `aggressiveness_max`            | `100`                                     | Maximum aggressiveness level.                                               |
| `attack_ranged_enabled`         | `1`                                       | Enables ranged attacks.                                                     |
| `attack_ranged_entity_file`     | `data/entities/projectiles/sniperbullet.xml` | File path for the projectile used in ranged attacks.                        |
| `attack_ranged_frames_between`  | `100`                                     | Frames to wait between ranged attacks.                                      |
| `attack_ranged_use_laser_sight` | `1`                                       | Enables a laser sight for ranged attacks.                                   |

### `DamageModelComponent`

Defines the Sniper's health and how it reacts to damage.

| Attribute                       | Value   | Description                                                              |
| :------------------------------ | :------ | :----------------------------------------------------------------------- |
| `hp`                            | `1.8`   | Hit points of the Sniper.                                                |
| `fire_probability_of_ignition`  | `5`     | Percentage chance to ignite from fire damage.                            |
| `ragdoll_filenames_file`        | `data/ragdolls/sniper/filenames.txt` | Specifies the ragdoll files used when the Sniper dies.                 |

### `SpriteComponent`

Determines the visual appearance of the Sniper.

| Attribute   | Value                      | Description                               |
| :---------- | :------------------------- | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/sniper.xml` | Path to the sprite's graphical data.      |

### `PathFindingComponent`

Configures the Sniper's movement capabilities, including jumping.

| Attribute                     | Value | Description                                                              |
| :---------------------------- | :---- | :----------------------------------------------------------------------- |
| `can_jump`                    | `1`   | Allows the Sniper to jump.                                               |
| `initial_jump_max_distance_x` | `60`  | Maximum horizontal distance the Sniper can jump.                         |
| `initial_jump_max_distance_y` | `50`  | Maximum vertical distance the Sniper can jump.                           |

**Jump Trajectories:** Defines specific jump arcs.

| x   | y   | lob |
| :-- | :-- | :-- |
| 5   | 15  | 1   |
| 7   | 20  | 1   |
| 10  | -30 | 1   |
| 40  | -35 | 1   |
| 50  | -40 | 1   |
| 60  | 75  | 1   |

### `CharacterPlatformingComponent`

Controls basic character movement parameters.

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `run_velocity` | `24`  | Horizontal movement speed.                |

### `HitboxComponent`

Defines the collision area for the Sniper.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_max_x` | `5`   | Maximum X-axis extent of the hitbox.      |
| `aabb_max_y` | `3`   | Maximum Y-axis extent of the hitbox.      |
| `aabb_min_x` | `-5`  | Minimum X-axis extent of the hitbox.      |
| `aabb_min_y` | `-12` | Minimum Y-axis extent of the hitbox.      |

## Additional Components

### `LightComponent`

Adds a light source to the Sniper.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `30`  | The radius of the light.                  |
| `r`       | `190` | Red component of the light color.         |
| `g`       | `200` | Green component of the light color.       |

### `SpriteComponent` (Laser Sight)

This component specifically handles the visual representation of the laser sight.

| Attribute   | Value                     | Description                               |
| :---------- | :------------------------ | :---------------------------------------- |
| `_tags`     | `laser_sight`             | Tag for identifying this sprite.          |
| `image_file` | `data/particles/laser_red.png` | Texture for the laser sight.              |
| `visible`   | `0`                       | Initially hidden until activated.         |

### `AudioComponent`

Manages the sound effects associated with the Sniper.

| Attribute   | Value                      | Description                               |
| :---------- | :------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | Path to the audio bank.                   |
| `event_root` | `animals/sniper`           | Root event name for Sniper sounds.        |

### `GameEffectComponent`

Applies a persistent game effect to the Sniper.

| Attribute | Value             | Description                               |
| :-------- | :---------------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE` | The type of game effect applied.          |
| `frames`  | `-1`              | Effect duration (infinite).               |