---
title: Icer Enemy Entity
category: entities
---

# Icer Enemy Entity

This document details the `icer.xml` entity, defining the behavior and attributes of the Icer enemy in Noita.

## Core Attributes

The Icer is a flying, robotic enemy with ice-themed attacks and resistances.

### `Entity` Name
- `$animal_icer`

### `Base` Entity
- `data/entities/base_enemy_robot.xml`: Inherits fundamental robot enemy properties.

## Key Components and Attributes

### `AnimalAIComponent`
Controls the Icer's artificial intelligence and combat behavior.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                        | Default AI behavior.                                                        |
| `escape_if_damaged_probability` | `4`                                 | Chance to flee when damaged.                                                |
| `attack_melee_damage_min`     | `0.4`                               | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`     | `0.7`                               | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`  | `400`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `400`                               | Vertical range for detecting creatures.                                     |
| `creature_detection_angular_range_deg` | `60`                                | Angular detection cone for creatures.                                       |
| `attack_melee_max_distance`   | `10`                                | Maximum distance for melee attacks.                                         |
| `food_material`               | `meat`                              | Material considered food (though `needs_food` is 0).                        |
| `needs_food`                  | `0`                                 | Does not require food to survive.                                           |
| `sense_creatures`             | `1`                                 | Actively senses nearby creatures.                                           |
| `can_fly`                     | `1`                                 | Capable of flight.                                                          |
| `aggressiveness_min`          | `1`                                 | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `60`                                | Maximum aggressiveness level.                                               |

### `DamageModelComponent`
Defines the Icer's health, resistances, and how it reacts to damage.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                          | `2`                                 | Hit points of the Icer.                                                     |
| `materials_create_messages`   | `1`                                 | Creates messages when damaged by certain materials.                         |
| `ragdoll_filenames_file`      | `data/ragdolls/icer/filenames.txt`  | Specifies the ragdoll files for the Icer.                                   |
| `fire_probability_of_ignition`| `0`                                 | Cannot be ignited by fire.                                                  |
| `ragdoll_material`            | `steel`                             | Material of the ragdoll.                                                    |
| `blood_material`              | `oil`                               | Material that acts as blood.                                                |
| `materials_that_damage`       | `acid,lava,poison`                  | Materials that inflict damage.                                              |
| `materials_how_much_damage`   | `0.004,0.004,0.001`                 | Damage multipliers for the listed materials.                                |

#### `damage_multipliers`
Specific damage resistances and vulnerabilities.

| Type  | Multiplier | Description                               |
| :---- | :--------- | :---------------------------------------- |
| `ice` | `0.0`      | Immune to ice damage.                     |

### `SpriteComponent`
Determines the visual appearance of the Icer.

- `image_file`: `data/enemies_gfx/icer.xml`

### `PathFindingComponent`
Governs the Icer's movement capabilities.

- `can_fly`: `1` (Can fly)
- `jump_speed`: `80`
- `initial_jump_max_distance_x`: `60`
- `initial_jump_max_distance_y`: `60`

### `CharacterPlatformingComponent`
Fine-tunes movement parameters like speed and acceleration.

- `fly_velocity_x`: `28`
- `run_velocity`: `20`
- `jump_velocity_y`: `-12`

### `HitboxComponent`
Defines the collision boundaries for the Icer.

- `aabb_max_x`: `5`
- `aabb_max_y`: `3`
- `aabb_min_x`: `-5`
- `aabb_min_y`: `-12`

### `ParticleEmitterComponent`
Responsible for emitting particles, likely for visual effects or propulsion.

- `emitted_material_name`: `rocket_particles`
- `create_real_particles`: `0`
- `emit_cosmetic_particles`: `1`
- `is_emitting`: `1`

### `LightComponent`
Adds a light source around the Icer.

- `radius`: `50`
- `r`, `g`, `b`: `120`, `120`, `200` (Blueish hue)

### `LuaComponent`
Allows for custom scripting.

- `script_death`: `data/scripts/animals/icer_death.lua` (Script executed on death)

### `AIAttackComponent`
Defines ranged attack behavior.

| Attribute                   | Value                               | Description                               |
| :-------------------------- | :---------------------------------- | :---------------------------------------- |
| `frames_between`            | `6`                                 | Delay between attacks.                    |
| `animation_name`            | `attack_ranged`                     | Animation used for ranged attacks.        |
| `attack_ranged_entity_file` | `data/entities/projectiles/icethrower.xml` | Projectile fired.                         |
| `min_distance`              | `30`                                | Minimum range for attack.                 |
| `max_distance`              | `140`                               | Maximum range for attack.                 |

### `GameEffectComponent`
Applies status effects to the Icer.

- `effect`: `PROTECTION_FREEZE` (Grants immunity to freezing)
- `frames`: `-1` (Permanent effect)