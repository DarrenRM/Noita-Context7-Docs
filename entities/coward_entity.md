---
title: Coward Entity
category: entities
---

# Coward Entity

This document details the configuration of the "Coward" entity in Noita, focusing on its AI, combat, and physical attributes.

## Core Attributes

The Coward entity is a flying creature with a strong tendency to flee rather than fight. It possesses a ranged attack but prioritizes evasion.

### `Base` Entity Configuration

The Coward inherits core functionalities from `base_enemy_flying.xml` and `base_jetpack.xml`.

### `AnimalAIComponent`

This component governs the creature's behavior.

| Attribute                       | Value                                     | Description                                                                 |
| :------------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                      | `1`                                       | Enables the AI component.                                                   |
| `preferred_job`                 | `JobDefault`                              | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability` | `100`                                     | Always attempts to escape when damaged.                                     |
| `attack_if_damaged_probability` | `0`                                       | Never attacks when damaged.                                                 |
| `creature_detection_range_x`    | `400`                                     | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`    | `300`                                     | Vertical range for detecting other creatures.                               |
| `sense_creatures`               | `1`                                       | Enables creature sensing.                                                   |
| `can_fly`                       | `1`                                       | Allows the creature to fly.                                                 |
| `attack_ranged_enabled`         | `0`                                       | Ranged attacks are disabled by default (but can be triggered).              |
| `attack_ranged_entity_file`     | `data/entities/projectiles/coward_bullet.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_frames_between`  | `60`                                      | Delay in frames between ranged attacks.                                     |
| `aggressiveness_min`            | `1`                                       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`            | `20`                                      | Maximum aggressiveness level.                                               |

### `DamageModelComponent`

Defines the entity's health and damage resistances.

| Attribute                   | Value   | Description                                       |
| :-------------------------- | :------ | :------------------------------------------------ |
| `hp`                        | `3`     | Hit points of the Coward.                         |
| `fire_probability_of_ignition` | `5`     | Chance of igniting from fire damage.              |
| `blood_spray_material`      | `blood` | The material used for blood spray effects.        |

#### `damage_multipliers`

| Type       | Value | Description                               |
| :--------- | :---- | :---------------------------------------- |
| `slice`    | `0.5` | Damage multiplier for slice damage.       |
| `projectile` | `0.5` | Damage multiplier for projectile damage.  |
| `explosion`| `0.8` | Damage multiplier for explosion damage.   |

### `SpriteComponent`

Determines the visual representation of the Coward.

| Attribute   | Value                           | Description                               |
| :---------- | :------------------------------ | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/coward.xml`   | Path to the sprite image file.            |

### `PathFindingComponent`

Configures how the entity navigates the environment.

| Attribute              | Value | Description                               |
| :--------------------- | :---- | :---------------------------------------- |
| `can_fly`              | `1`   | Allows pathfinding while flying.          |
| `initial_jump_lob`     | `1`   | Controls the arc of jumps.                |
| `initial_jump_max_distance_x` | `60`  | Maximum horizontal jump distance.         |
| `initial_jump_max_distance_y` | `60`  | Maximum vertical jump distance.           |

### `CharacterPlatformingComponent`

Defines movement parameters for the character.

| Attribute       | Value | Description                               |
| :-------------- | :---- | :---------------------------------------- |
| `fly_speed_change_spd` | `0.8` | Speed change multiplier when flying.      |
| `fly_velocity_x` | `45`  | Horizontal velocity when flying.          |
| `run_velocity`  | `25`  | Horizontal velocity when running.         |

### `HitboxComponent`

Defines the collision area for the entity.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-5`  | Minimum X-axis bounding box coordinate.   |
| `aabb_max_x`| `5`   | Maximum X-axis bounding box coordinate.   |
| `aabb_min_y`| `-12` | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_y`| `3`   | Maximum Y-axis bounding box coordinate.   |

## Additional Components

### `ItemChestComponent`

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `level`   | `2`   | Loot chest level.                         |

### `GenomeDataComponent`

| Attribute       | Value | Description                               |
| :-------------- | :---- | :---------------------------------------- |
| `herd_id`       | `healer`| Identifier for its herd.                  |
| `food_chain_rank`| `9`   | Position in the food chain.               |
| `is_predator`   | `1`   | Indicates if it's a predator.             |

### `LightComponent`

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `radius`    | `50`  | The radius of the light emitted.          |
| `fade_out_time`| `1.5` | Time it takes for the light to fade out.  |

### `ItemPickUpperComponent`

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `is_in_npc` | `1`   | Indicates if it's part of an NPC.         |

### `AudioComponent`

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | Path to the audio bank file.              |
| `event_root`| `animals/scavenger`                 | Root event name for audio.                |

### `GameEffectComponent`

| Attribute | Value           | Description                               |
| :-------- | :-------------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE` | Applies a radioactive allergy effect.     |
| `frames`  | `-1`            | Effect duration (infinite).               |

### `LuaComponent`

| Attribute             | Value                                 | Description                               |
| :-------------------- | :------------------------------------ | :---------------------------------------- |
| `script_source_file`  | `data/scripts/animals/coward_check.lua` | Path to the custom Lua script.            |
| `execute_every_n_frame`| `40`                                  | How often the script is executed.         |

### `Base file="data/entities/misc/animal_energy_shield.xml"`

This indicates the Coward entity utilizes an energy shield, likely for defensive purposes.