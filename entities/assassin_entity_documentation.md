---
title: Assassin Entity Documentation
category: entities
---

---

# Assassin Entity Documentation

This document details the configuration of the Assassin enemy entity in Noita, focusing on its AI, combat, and physical attributes for modding purposes.

## Core Attributes

The Assassin is a fast, flying robot enemy with aggressive melee and dash attacks. It prioritizes hiding from prey and has a moderate health pool.

### `Base` Entity Configuration

The Assassin inherits from `base_enemy_robot.xml`, gaining fundamental robot enemy properties.

### `AnimalAIComponent`

This component governs the Assassin's behavior and combat routines.

| Attribute                     | Description                                                                 | Value Examples        |
| :---------------------------- | :-------------------------------------------------------------------------- | :-------------------- |
| `escape_if_damaged_probability` | Probability of attempting to flee when damaged.                             | `0` (Never flees)     |
| `hide_from_prey`              | Whether the AI attempts to hide from its current target.                    | `1` (Enabled)         |
| `hide_from_prey_target_distance` | Distance at which the AI will attempt to hide.                              | `200`                 |
| `hide_from_prey_time`         | Duration (in frames) the AI will remain hidden.                             | `480`                 |
| `attack_melee_damage_min`     | Minimum damage for melee attacks.                                           | `1.0`                 |
| `attack_melee_damage_max`     | Maximum damage for melee attacks.                                           | `1.6`                 |
| `attack_dash_enabled`         | Enables the dash attack.                                                    | `1` (Enabled)         |
| `attack_dash_lob`             | Controls the arc/trajectory of the dash attack.                             | `1.1`                 |
| `attack_dash_damage`          | Damage dealt by the dash attack.                                            | `0.9`                 |
| `needs_food`                  | Whether the entity requires food.                                           | `0` (Does not need)   |
| `can_fly`                     | Allows the entity to fly.                                                   | `1` (Enabled)         |
| `aggressiveness_min`          | Minimum aggressiveness level.                                               | `1`                   |
| `aggressiveness_max`          | Maximum aggressiveness level.                                               | `50`                  |

### `SpriteComponent` (Primary)

Defines the main visual appearance of the Assassin.

| Attribute     | Description                               | Value Example                     |
| :------------ | :---------------------------------------- | :-------------------------------- |
| `image_file`  | Path to the sprite's texture atlas.       | `data/enemies_gfx/assassin.xml`   |
| `offset_x`    | Horizontal offset for the sprite.         | `8`                               |
| `offset_y`    | Vertical offset for the sprite.           | `13`                              |

### `DamageModelComponent`

Manages health, damage resistance, and ragdoll properties.

| Attribute                     | Description                               | Value Example       |
| :---------------------------- | :---------------------------------------- | :------------------ |
| `hp`                          | Hit points of the entity.                 | `8`                 |
| `ragdoll_material`            | Material used for the ragdoll.            | `steel`             |
| `ragdoll_filenames_file`      | File listing ragdoll sprite frames.       | `data/ragdolls/assassin/filenames.txt` |
| `blood_material`              | Material of the blood spray.              | `oil`               |
| `blood_spray_material`        | Material of the blood spray.              | `oil`               |
| `fire_probability_of_ignition`| Probability of catching fire.             | `0` (Cannot ignite) |

### `PathFindingComponent`

Determines how the entity navigates the environment.

| Attribute           | Description                               | Value Example |
| :------------------ | :---------------------------------------- | :------------ |
| `can_jump`          | Allows the entity to jump.                | `1` (Enabled) |
| `can_fly`           | Allows the entity to fly.                 | `1` (Enabled) |
| `frames_to_get_stuck` | Frames before entity is considered stuck. | `20`          |

### `CharacterPlatformingComponent`

Controls movement parameters like speed and acceleration.

| Attribute        | Description                               | Value Example |
| :--------------- | :---------------------------------------- | :------------ |
| `jump_velocity_y`| Vertical velocity applied when jumping.   | `-140`        |
| `run_velocity`   | Base running speed.                       | `31`          |
| `fly_speed_change_spd` | Speed modifier for flying.            | `0.8`         |
| `fly_velocity_x` | Horizontal speed when flying.             | `28`          |
| `accel_x`        | Horizontal acceleration.                  | `0.03`        |

### `GenomeDataComponent`

Defines the entity's place in the ecosystem.

| Attribute         | Description                               | Value Example |
| :---------------- | :---------------------------------------- | :------------ |
| `herd_id`         | Identifier for its species/group.         | `robot`       |
| `food_chain_rank` | Position in the food chain.               | `5`           |
| `is_predator`     | Whether the entity is a predator.         | `1` (True)    |

### `CharacterDataComponent`

Defines collision bounds and mass.

| Attribute           | Description                               | Value Example |
| :------------------ | :---------------------------------------- | :------------ |
| `collision_aabb_min_x` | Minimum X coordinate for collision box. | `-3.0`        |
| `collision_aabb_max_x` | Maximum X coordinate for collision box. | `3.0`         |
| `collision_aabb_min_y` | Minimum Y coordinate for collision box. | `-9`          |
| `collision_aabb_max_y` | Maximum Y coordinate for collision box. | `3`           |
| `mass`              | Mass of the entity.                       | `1.8`         |

## Visual and Effect Components

### `SpriteComponent` (Emissive)

Adds an emissive glow effect to the Assassin.

| Attribute     | Description                               | Value Example                     |
| :------------ | :---------------------------------------- | :-------------------------------- |
| `image_file`  | Path to the emissive sprite texture.      | `data/enemies_gfx/assassin_emissive.xml` |
| `offset_x`    | Horizontal offset for the sprite.         | `8`                               |
| `offset_y`    | Vertical offset for the sprite.           | `13`                              |
| `emissive`    | Enables emissive lighting.                | `1` (Enabled)                     |
| `additive`    | Uses additive blending for the emissive effect. | `1` (Enabled)                     |
| `rect_animation`| Name of the sprite animation to use.      | `walk`                            |

### `ParticleEmitterComponent` (`jetpack`)

Simulates jetpack exhaust particles.

| Attribute               | Description                               | Value Example |
| :---------------------- | :---------------------------------------- | :------------ |
| `emitted_material_name` | Material of the emitted particles.        | `rocket_particles` |
| `offset.x`              | X offset of the emitter.                  | `-4`          |
| `offset.y`              | Y offset of the emitter.                  | `-4`          |
| `x_vel_min`             | Minimum X velocity of particles.          | `-7`          |
| `x_vel_max`             | Maximum X velocity of particles.          | `7`           |
| `y_vel_min`             | Minimum Y velocity of particles.          | `80`          |
| `y_vel_max`             | Maximum Y velocity of particles.          | `180`         |
| `count_min`             | Minimum number of particles emitted per burst. | `3`           |
| `count_max`             | Maximum number of particles emitted per burst. | `7`           |
| `lifetime_min`          | Minimum particle lifetime (seconds).      | `0.1`         |
| `lifetime_max`          | Maximum particle lifetime (seconds).      | `0.2`         |
| `emit_cosmetic_particles`| Whether to emit cosmetic particles.       | `1` (Enabled) |
| `is_emitting`           | Whether the emitter is active.            | `1` (Enabled) |

### `ItemPickUpperComponent`

Allows the entity to pick up items.

| Attribute   | Description                 | Value Example |
| :---------- | :-------------------------- | :------------ |
| `is_in_npc` | Indicates it's an NPC.      | `1` (True)    |

### `Entity` (Energy Shield)

Applies a protective energy shield effect.

*   Inherits from `data/entities/misc/animal_energy_shield_sector.xml`.

### `AudioComponent`

Manages general sound effects.

| Attribute   | Description                               | Value Example             |
| :---------- | :---------------------------------------- | :------------------------ |
| `file`      | Path to the audio bank.                   | `data/audio/Desktop/animals.bank` |
| `event_root`| Root event name for the entity's sounds.  | `animals/assassin`        |

### `AudioLoopComponent`

Handles looping ambient sounds.

| Attribute     | Description                               | Value Example             |
| :------------ | :---------------------------------------- | :------------------------ |
| `file`        | Path to the audio bank.                   | `data/audio/Desktop/animals.bank` |
| `event_name`  | Name of the looping sound event.          | `animals/assassin/movement_loop` |
| `auto_play`   | Whether the sound plays automatically.    | `1` (Enabled)             |

### `Entity` (Freeze Protection)

Grants immunity to freezing.

*   Applies `PROTECTION_FREEZE` effect with a duration of `-1` (permanent).