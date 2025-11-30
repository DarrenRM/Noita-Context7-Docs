---
title: Drone Entity
category: entities
---

# Drone Entity

This document details the `drone.xml` entity, a flying robotic enemy in Noita. It focuses on key attributes relevant for AI-assisted modding.

## Core Components

The drone entity is built upon a `Base` entity, inheriting its fundamental properties.

### `Base file="data/entities/base_enemy_robot.xml"`

This indicates the drone inherits from a generic robot enemy template.

## Key Attributes

### `AnimalAIComponent`

This component governs the drone's behavior and AI.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `creature_detection_range_x`  | `250`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `250`                               | Vertical range for detecting creatures.                                     |
| `attack_ranged_min_distance`  | `0`                                 | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`  | `100`                               | Maximum distance for ranged attacks.                                        |
| `food_material`               | `blood`                             | Material the drone consumes (though `needs_food` is disabled).              |
| `needs_food`                  | `0`                                 | Whether the drone requires food to survive (disabled).                      |
| `sense_creatures`             | `1`                                 | Enables creature sensing.                                                   |
| `attack_ranged_enabled`       | `1`                                 | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `1`                                 | Enables melee attacks.                                                      |
| `can_fly`                     | `1`                                 | Allows the drone to fly.                                                    |
| `can_walk`                    | `0`                                 | Disables walking.                                                           |
| `attack_ranged_entity_file`   | `data/entities/projectiles/orb_blue.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_frames_between`| `40`                                | Frames between consecutive ranged attacks.                                  |

### `DamageModelComponent`

Defines the drone's health and damage-related properties.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                          | `0.4`                               | Hit points of the drone.                                                    |
| `ragdoll_filenames_file`      | `data/ragdolls/drone/filenames.txt` | File defining the drone's ragdoll appearance upon death.                    |
| `fire_probability_of_ignition`| `0`                                 | Probability of igniting from fire (set to 0).                               |
| `ragdoll_material`            | `gunpowder_unstable`                | Material of the ragdoll, potentially affecting its behavior when destroyed. |

### `SpriteComponent`

Handles the visual representation of the drone.

| Attribute      | Value                           | Description                               |
| :------------- | :------------------------------ | :---------------------------------------- |
| `image_file`   | `data/enemies_gfx/drone.xml`    | Path to the drone's sprite definition.    |
| `offset_x`     | `0`                             | Horizontal offset of the sprite.          |
| `offset_y`     | `0`                             | Vertical offset of the sprite.            |

### `PathFindingComponent`

Determines how the drone navigates the environment.

| Attribute | Value | Description             |
| :-------- | :---- | :---------------------- |
| `can_fly` | `1`   | Allows flight pathfinding. |
| `can_walk`| `0`   | Disables walking pathfinding. |

### `CharacterPlatformingComponent`

Controls the drone's movement physics, including flight.

| Attribute           | Value | Description                                     |
| :------------------ | :---- | :---------------------------------------------- |
| `fly_speed_max_up`  | `60`  | Maximum upward flight speed.                    |
| `fly_speed_max_down`| `60`  | Maximum downward flight speed.                  |
| `fly_speed_mult`    | `18`  | Multiplier for flight speed.                    |
| `fly_velocity_x`    | `60`  | Horizontal flight velocity.                     |

### `HitboxComponent`

Defines the collision area for the drone.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-6`  | Minimum X-coordinate of the bounding box. |
| `aabb_min_y`| `-9`  | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x`| `6`   | Maximum X-coordinate of the bounding box. |
| `aabb_max_y`| `1`   | Maximum Y-coordinate of the bounding box. |

### `AudioLoopComponent`

Manages the drone's sound effects.

| Attribute   | Value                                | Description                                     |
| :---------- | :----------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`    | Path to the audio bank.                         |
| `event_name`| `animals/drone/movement_loop`        | The specific audio event for movement loop.     |
| `auto_play` | `1`                                  | Starts playing the sound automatically.         |

### `GameEffectComponent`

Applies status effects to the drone.

| Attribute | Value         | Description                                     |
| :-------- | :------------ | :---------------------------------------------- |
| `effect`  | `PROTECTION_FREEZE` | Grants immunity to freezing.                    |
| `frames`  | `-1`          | Effect is permanent (lasts indefinitely).       |