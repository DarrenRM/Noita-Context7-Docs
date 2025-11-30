---
title: Necrobot Super Entity
category: entities
---

---

# Necrobot Super Entity

This document details the configuration for the "Necrobot Super" entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Core Components

The Necrobot Super is a flying, aggressive robot enemy with ranged attack capabilities.

### Base Enemy Robot Configuration

The entity inherits from `data/entities/base_enemy_robot.xml`, providing fundamental robot behaviors.

### AnimalAIComponent

This component governs the AI and combat behavior of the Necrobot Super.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `creature_detection_range_x`  | 300     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | 300     | Vertical range for detecting creatures.                                     |
| `can_fly`                     | 1       | Enables flight capabilities.                                                |
| `aggressiveness_min`          | 1       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | 100     | Maximum aggressiveness level.                                               |
| `attack_ranged_enabled`       | 1       | Enables ranged attacks.                                                     |
| `attack_landing_ranged_enabled` | 1       | Enables ranged attacks while landing.                                       |
| `attack_ranged_action_frame`  | 5       | Frame within the attack animation when the projectile is fired.             |
| `attack_ranged_min_distance`  | 0       | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`  | 220     | Maximum distance for ranged attacks.                                        |
| `attack_ranged_entity_file`   | `data/entities/projectiles/dotshot_strong.xml` | The projectile entity used for ranged attacks. |
| `attack_ranged_frames_between`| 80      | Frames between consecutive ranged attacks.                                  |
| `attack_ranged_offset_x`      | 2       | X-axis offset for projectile spawn.                                         |
| `attack_ranged_offset_y`      | -4      | Y-axis offset for projectile spawn.                                         |

### SpriteComponent

Defines the visual appearance of the Necrobot Super.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/necrobot_super.xml` | Path to the sprite's image file.          |
| `offset_x`   | 0                                   | X-axis offset for the sprite.             |
| `offset_y`   | 0                                   | Y-axis offset for the sprite.             |

### DamageModelComponent

Manages health, damage resistances, and knockback properties.

| Attribute                     | Value   | Description                                                                 |
| :---------------------------- | :------ | :-------------------------------------------------------------------------- |
| `hp`                          | 28      | Hit points of the entity.                                                   |
| `ragdoll_material`            | steel   | Material used for the ragdoll effect.                                       |
| `blood_material`              | oil     | Material of the "blood" when damaged.                                       |
| `fire_probability_of_ignition`| 0       | Probability of catching fire.                                               |
| `minimum_knockback_force`     | 100000  | Minimum force required to knock back the entity.                            |
| `holy` (in `damage_multipliers`)| 1.2     | Multiplier for holy damage taken.                                           |

### PathFindingComponent

Controls how the entity navigates the game world.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `can_jump`| 1     | Allows the entity to jump.                |
| `can_fly` | 1     | Allows the entity to fly.                 |

### CharacterPlatformingComponent

Defines movement parameters for characters.

| Attribute        | Value | Description                               |
| :--------------- | :---- | :---------------------------------------- |
| `jump_velocity_y`| -100  | Vertical velocity when jumping.           |
| `run_velocity`   | 18    | Horizontal movement speed.                |
| `fly_velocity_x` | 28    | Horizontal flight speed.                  |

### GenomeDataComponent

Provides genetic information for creature interactions and AI.

| Attribute       | Value | Description                               |
| :-------------- | :---- | :---------------------------------------- |
| `herd_id`       | robot | Identifier for its herd/faction.          |
| `food_chain_rank`| 5     | Position in the food chain.               |
| `is_predator`   | 1     | Indicates if it's a predator.             |

## Visual and Effect Components

These components add visual flair and special effects to the Necrobot Super.

### Emissive Sprite Component

Adds an emissive glow to the entity.

| Attribute    | Value                                     | Description                               |
| :----------- | :---------------------------------------- | :---------------------------------------- |
| `image_file` | `data/enemies_gfx/necrobot_super_emissive.xml` | Path to the emissive sprite's image file. |
| `emissive`   | 1                                         | Enables emissive properties.              |
| `additive`   | 1                                         | Enables additive blending for the glow.   |
| `rect_animation`| walk                                      | The name of the sprite's walk animation.  |

### Particle Emitter Components

These components generate visual effects like jetpack trails and smoke.

*   **Jetpack Particles:**
    *   `emitted_material_name`: `rocket_particles`
    *   `offset.x`: -4
    *   `offset.y`: -4
    *   `y_vel_min`: 80
    *   `y_vel_max`: 180
    *   `lifetime_min`: 0.1
    *   `lifetime_max`: 0.2
    *   `create_real_particles`: 0 (cosmetic only)
    *   `is_emitting`: 1

*   **Smoke Particles:**
    *   `emitted_material_name`: `smoke`
    *   `offset.x`: 0
    *   `offset.y`: 0
    *   `y_vel_min`: 80
    *   `y_vel_max`: 180
    *   `lifetime_min`: 0.1
    *   `lifetime_max`: 0.2
    *   `create_real_particles`: 1
    *   `emission_interval_min_frames`: 3
    *   `emission_interval_max_frames`: 5
    *   `is_emitting`: 1

## Other Components

### LuaComponent

*   `script_source_file`: `data/scripts/animals/necrobot_super.lua`
*   `execute_every_n_frame`: 40

This component links custom Lua scripting for advanced behaviors.

### AudioComponent & AudioLoopComponent

These components manage the sound effects and looping audio for the Necrobot Super, including movement and attack sounds.

### Entity: GameEffectComponent

*   `effect`: `PROTECTION_FREEZE`
*   `frames`: -1

Applies a permanent freeze protection effect to the entity.