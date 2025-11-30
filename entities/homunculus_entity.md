---
title: Homunculus Entity
category: entities
---

# Homunculus Entity

This document details the configuration of the Homunculus entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Attributes

The Homunculus is a flying, aggressive creature with ranged attack capabilities.

### `AnimalAIComponent`

This component governs the creature's behavior and AI.

| Attribute                      | Value                                     | Description                                                                 |
| :----------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`                | `JobDefault`                              | Default job assigned to the creature.                                       |
| `attack_melee_enabled`         | `0`                                       | Melee attacks are disabled.                                                 |
| `escape_if_damaged_probability`| `0`                                       | Does not attempt to escape when damaged.                                    |
| `attack_if_damaged_probability`| `0`                                       | Does not specifically attack when damaged (relies on general aggression).   |
| `creature_detection_range_x`   | `400`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`   | `400`                                     | Vertical range for detecting creatures.                                     |
| `dont_counter_attack_own_herd` | `1`                                       | Will not counter-attack members of its own herd.                            |
| `food_material`                | `blood`                                   | The material the creature considers food.                                   |
| `needs_food`                   | `0`                                       | The creature does not require food to survive.                              |
| `sense_creatures`              | `1`                                       | Actively senses other creatures.                                            |
| `attack_ranged_enabled`        | `1`                                       | Ranged attacks are enabled.                                                 |
| `can_fly`                      | `1`                                       | The creature can fly.                                                       |
| `attack_ranged_entity_file`    | `data/entities/projectiles/fireball_firebug.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_action_frame`   | `3`                                       | The frame at which the ranged attack action is performed.                   |
| `attack_ranged_frames_between` | `80`                                      | Number of frames between ranged attacks.                                    |
| `attack_ranged_max_distance`   | `200`                                     | Maximum distance for ranged attacks.                                        |
| `aggressiveness_min`           | `95`                                      | Minimum aggression level.                                                   |
| `aggressiveness_max`           | `100`                                     | Maximum aggression level.                                                   |

### `DamageModelComponent`

Defines the health and damage resistances of the Homunculus.

| Attribute                 | Value  | Description                               |
| :------------------------ | :----- | :---------------------------------------- |
| `hp`                      | `2.0`  | Hit points of the Homunculus.             |
| `ragdoll_material`        | `meat` | Material used for its ragdoll.            |
| `fire_probability_of_ignition` | `0` | Cannot be ignited by fire.                |

#### `damage_multipliers`

| Damage Type | Multiplier |
| :---------- | :--------- |
| `fire`      | `0.5`      |
| `slice`     | `0.5`      |
| `melee`     | `0.5`      |
| `projectile`| `0.5`      |
| `explosion` | `0.5`      |

### `SpriteComponent`

Specifies the visual representation of the Homunculus.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/homunculus.xml`   | Path to the sprite definition file.       |

### `CharacterPlatformingComponent`

Controls movement and platforming abilities.

| Attribute      | Value | Description                               |
| :------------- | :---- | :---------------------------------------- |
| `jump_velocity_y`| `-12` | Vertical velocity when jumping.           |
| `run_velocity` | `18`  | Horizontal movement speed.                |

### `HitboxComponent`

Defines the collision area for interactions.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-4.5`| Minimum X-axis extent of the hitbox.      |
| `aabb_max_x`| `4.5` | Maximum X-axis extent of the hitbox.      |
| `aabb_min_y`| `-10` | Minimum Y-axis extent of the hitbox.      |
| `aabb_max_y`| `3`   | Maximum Y-axis extent of the hitbox.      |

## Special Components

### `Base file="data/entities/base_enemy_basic.xml"`

Inherits fundamental properties from a basic enemy template.

### `Entity` (Jetpack)

The Homunculus is equipped with a jetpack for flight.

### `AudioComponent`

Manages sound effects for the Homunculus.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | Path to the audio bank.                   |
| `event_root`| `animals/homunculus`                | Root event name for Homunculus sounds.    |

### `LuaComponent` (Scripts)

Custom Lua scripts control specific behaviors.

| Script File                                          | Execute Every N Frame | Remove After Executed | Description                                                              |
| :--------------------------------------------------- | :-------------------- | :-------------------- | :----------------------------------------------------------------------- |
| `data/scripts/streaming_integration/scripts/homunculus_init.lua` | `1`                   | `1`                   | Initialization script, runs once.                                        |
| `data/scripts/streaming_integration/scripts/homunculus_teleport.lua` | `120`                 |                       | Script for teleportation behavior, runs periodically.                    |
| `data/scripts/animals/homunculus_attack.lua`         | `-1`                  |                       | Handles the Homunculus's attack logic.                                   |

### `Entity` (Charm Effect)

The Homunculus applies a "CHARM" effect to entities it interacts with.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `effect`  | `CHARM` | The game effect applied.                  |
| `frames`  | `-1`  | The effect lasts indefinitely.            |