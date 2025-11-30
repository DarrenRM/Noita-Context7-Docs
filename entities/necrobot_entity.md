---
title: Necrobot Entity
category: entities
---

---

# Necrobot Entity

This document details the configuration of the Necrobot entity in Noita, focusing on its AI, combat, and visual properties for AI-assisted modding.

## Core Components

The Necrobot is a flying robotic enemy with ranged attack capabilities.

### Base Entity Configuration

The Necrobot inherits from `base_enemy_robot.xml`, providing fundamental robot behaviors.

### AnimalAIComponent

This component governs the Necrobot's artificial intelligence and combat actions.

| Attribute                     | Value                                     | Description                                                                 |
| :---------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `escape_if_damaged_probability` | `0`                                       | Necrobot does not attempt to flee when damaged.                             |
| `attack_dash_enabled`         | `0`                                       | Dash attack is disabled.                                                    |
| `attack_melee_enabled`        | `0`                                       | Melee attack is disabled.                                                   |
| `creature_detection_range_x`  | `300`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `300`                                     | Vertical range for detecting creatures.                                     |
| `needs_food`                  | `0`                                       | Necrobot does not require food.                                             |
| `can_fly`                     | `1`                                       | Necrobot is capable of flight.                                              |
| `aggressiveness_min`          | `1`                                       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`          | `100`                                     | Maximum aggressiveness level.                                               |
| `attack_ranged_enabled`       | `1`                                       | Ranged attack is enabled.                                                   |
| `attack_landing_ranged_enabled` | `1`                                       | Ranged attack is enabled while landing.                                     |
| `attack_ranged_action_frame`  | `5`                                       | Frame at which the ranged attack is initiated.                              |
| `attack_ranged_min_distance`  | `0`                                       | Minimum distance for ranged attack.                                         |
| `attack_ranged_max_distance`  | `220`                                     | Maximum distance for ranged attack.                                         |
| `attack_ranged_entity_file`   | `data/entities/projectiles/dotshot.xml`   | Projectile entity used for ranged attacks.                                  |
| `attack_ranged_frames_between`| `80`                                      | Frames between consecutive ranged attacks.                                  |
| `attack_ranged_offset_x`      | `2`                                       | Horizontal offset for projectile origin.                                    |
| `attack_ranged_offset_y`      | `-4`                                      | Vertical offset for projectile origin.                                      |

### SpriteComponent

Defines the visual appearance of the Necrobot.

| Attribute    | Value                               | Description                                     |
| :----------- | :---------------------------------- | :---------------------------------------------- |
| `image_file` | `data/enemies_gfx/necrobot.xml`     | Primary sprite sheet for the Necrobot.          |
| `offset_x`   | `0`                                 | Horizontal sprite offset.                       |
| `offset_y`   | `0`                                 | Vertical sprite offset.                         |

### DamageModelComponent

Manages the Necrobot's health and damage properties.

| Attribute                     | Value           | Description                                                              |
| :---------------------------- | :-------------- | :----------------------------------------------------------------------- |
| `hp`                          | `16`            | Hit points of the Necrobot.                                              |
| `ragdoll_material`            | `steel`         | Material used for the ragdoll when defeated.                             |
| `ragdoll_filenames_file`      | `...filenames.txt` | File specifying ragdoll sprite names.                                    |
| `blood_material`              | `oil`           | Material of the "blood" it spills.                                       |
| `blood_spray_material`        | `oil`           | Material of the "blood" spray.                                           |
| `fire_probability_of_ignition`| `0`             | Necrobot cannot be ignited by fire.                                      |
| `minimum_knockback_force`     | `100000`        | Minimum force required to knock back the Necrobot.                       |
| `holy`                        | `1.2`           | Damage multiplier for holy damage types.                                 |

### PathFindingComponent

Determines how the Necrobot navigates the game world.

| Attribute       | Value | Description                               |
| :-------------- | :---- | :---------------------------------------- |
| `can_jump`      | `1`   | Necrobot can jump.                        |
| `can_fly`       | `1`   | Necrobot can fly.                         |
| `frames_to_get_stuck` | `20`  | Frames before considering itself stuck. |

### HitboxComponent

Defines the collision boundaries of the Necrobot.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_max_x`| `4`   | Maximum X-coordinate of the bounding box. |
| `aabb_max_y`| `2`   | Maximum Y-coordinate of the bounding box. |
| `aabb_min_x`| `-4`  | Minimum X-coordinate of the bounding box. |
| `aabb_min_y`| `-16` | Minimum Y-coordinate of the bounding box. |

### CharacterPlatformingComponent

Controls movement and physics related to character movement.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `jump_velocity_y` | `-100`| Vertical velocity applied when jumping.   |
| `run_velocity`    | `18`  | Base running speed.                       |
| `fly_speed_change_spd` | `0.8` | Speed modifier for flying.                |
| `fly_velocity_x`  | `28`  | Horizontal speed while flying.            |
| `accel_x`         | `0.03`| Horizontal acceleration.                  |

### GenomeDataComponent

Information related to the Necrobot's place in the game's ecosystem.

| Attribute        | Value  | Description                               |
| :--------------- | :----- | :---------------------------------------- |
| `herd_id`        | `robot`| Identifier for its group.                 |
| `food_chain_rank`| `5`    | Position in the food chain.               |
| `is_predator`    | `1`    | Indicates it is a predator.               |

### CharacterDataComponent

General character properties.

| Attribute            | Value | Description                               |
| :------------------- | :---- | :---------------------------------------- |
| `collision_aabb_min_x`| `-3.0`| Minimum X for collision box.              |
| `collision_aabb_max_x`| `3.0` | Maximum X for collision box.              |
| `collision_aabb_min_y`| `-9`  | Minimum Y for collision box.              |
| `collision_aabb_max_y`| `3`   | Maximum Y for collision box.              |
| `mass`               | `1.8` | Mass of the character.                    |

## Visual and Effect Components

### Emissive Sprite Component

Adds an emissive glow effect to the Necrobot.

| Attribute    | Value                                 | Description                                     |
| :----------- | :------------------------------------ | :---------------------------------------------- |
| `image_file` | `data/enemies_gfx/necrobot_emissive.xml`| Sprite sheet for the emissive effect.           |
| `emissive`   | `1`                                   | Enables emissive rendering.                     |
| `additive`   | `1`                                   | Uses additive blending for the emissive effect. |
| `rect_animation`| `walk`                                | Specifies the animation to use.                 |

### Particle Emitter Components

These components generate visual effects.

*   **Jetpack Particles:**
    *   `emitted_material_name`: `rocket_particles`
    *   `offset.x`: `-4`, `offset.y`: `-4`
    *   `x_vel_min`: `-7`, `x_vel_max`: `7`
    *   `y_vel_min`: `80`, `y_vel_max`: `180`
    *   `count_min`: `3`, `count_max`: `7`
    *   `lifetime_min`: `0.1`, `lifetime_max`: `0.2`
    *   `emit_cosmetic_particles`: `1` (visual only)
    *   `is_emitting`: `1`

*   **Smoke Particles:**
    *   `emitted_material_name`: `smoke`
    *   `offset.x`: `0`, `offset.y`: `0`
    *   `x_vel_min`: `-7`, `x_vel_max`: `7`
    *   `y_vel_min`: `80`, `y_vel_max`: `180`
    *   `count_min`: `1`, `count_max`: `2`
    *   `lifetime_min`: `0.1`, `lifetime_max`: `0.2`
    *   `create_real_particles`: `1` (can interact with world)
    *   `emission_interval_min_frames`: `3`, `emission_interval_max_frames`: `5`
    *   `is_emitting`: `1`

### ItemPickUpperComponent

Allows the Necrobot to pick up items.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `is_in_npc` | `1`   | Indicates it's part of an NPC.            |

### HotspotComponent

Defines interaction points, such as for holding items.

| Attribute            | Value | Description                               |
| :------------------- | :---- | :---------------------------------------- |
| `sprite_hotspot_name`| `hand`| Name of the sprite hotspot.               |

### Energy Shield Sector

The Necrobot utilizes a protective energy shield.

*   Inherits from `data/entities/misc/animal_energy_shield_sector.xml`.

### Audio Components

Handles sound effects for the Necrobot.

*   **Main Audio Bank:**
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_root`: `animals/assassin` (for general sounds)
*   **Movement Loop 1:**
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_name`: `animals/tank/movement_loop`
    *   `auto_play`: `1`
*   **Movement Loop 2:**
    *   `file`: `data/audio/Desktop/animals.bank`
    *   `event_name`: `animals/assassin/movement_loop`
    *   `auto_play`: `1`

### GameEffectComponent

Applies a game effect to the Necrobot.

| Attribute | Value          | Description                               |
| :-------- | :------------- | :---------------------------------------- |
| `effect`  | `PROTECTION_FREEZE`| Grants immunity to freezing.              |
| `frames`  | `-1`           | Effect is permanent.                      |

### LuaComponent

Integrates custom Lua scripting for advanced behaviors.

| Attribute           | Value                                | Description                               |
| :------------------ | :----------------------------------- | :---------------------------------------- |
| `script_source_file`| `data/scripts/animals/necrobot.lua`  | Path to the Necrobot's Lua script.        |
| `execute_every_n_frame`| `40`                                 | How often the script is executed.         |