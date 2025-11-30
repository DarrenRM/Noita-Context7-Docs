---
title: Tank Super Enemy Entity
category: entities
---

# Tank Super Enemy Entity

This document details the configuration of the "Tank Super" enemy entity in Noita, focusing on its attributes relevant to AI-driven modding.

## Core Attributes

The `Tank Super` is a robust robotic enemy with distinct offensive and defensive capabilities.

### Base Enemy Robot Configuration

The entity inherits core functionalities from `data/entities/base_enemy_robot.xml`.

### AnimalAIComponent

This component governs the creature's behavior and AI.

| Attribute                       | Value                               | Description                                                                 |
| :------------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault`                        | The primary job assigned to this AI.                                        |
| `escape_if_damaged_probability` | `0`                                 | This enemy will not attempt to flee when damaged.                           |
| `attack_melee_damage_min`       | `0.4`                               | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | `0.7`                               | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`    | `600`                               | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `600`                               | Vertical range for detecting creatures.                                     |
| `attack_ranged_min_distance`    | `0`                                 | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`    | `450`                               | Maximum distance for ranged attacks.                                        |
| `food_material`                 | `blood`                             | The material this creature consumes for sustenance (though `needs_food` is 0). |
| `needs_food`                    | `0`                                 | This creature does not require food.                                        |
| `sense_creatures`               | `1`                                 | The creature is capable of sensing other creatures.                         |
| `attack_melee_enabled`          | `0`                                 | Melee attacks are disabled for this entity.                                 |
| `aggressiveness_min`            | `1`                                 | Minimum aggressiveness level.                                               |
| `aggressiveness_max`            | `95`                                | Maximum aggressiveness level.                                               |

### DamageModelComponent

Defines the entity's health, resistances, and how it takes damage.

| Attribute                       | Value                               | Description                                                                 |
| :------------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                            | `25.5`                              | Hit points of the entity.                                                   |
| `ragdoll_material`              | `steel`                             | The material used for the ragdoll effect upon death.                        |
| `blood_material`                | `oil`                               | The material that spills out when damaged (acts as blood).                  |
| `fire_probability_of_ignition`  | `0`                                 | Cannot be ignited by fire.                                                  |
| `in_liquid_shooting_electrify_prob` | `30`                              | Probability of electrifying when shooting in liquid.                        |
| `minimum_knockback_force`       | `100000`                            | Minimum force required to knock this entity back.                           |

#### Damage Multipliers

| Damage Type | Multiplier |
| :---------- | :--------- |
| `projectile`| `0.5`      |
| `explosion` | `0.6`      |
| `electricity`| `1.6`      |
| `fire`      | `0.1`      |

### SpriteComponent

Manages the visual representation of the entity.

| Attribute     | Value                                | Description                                                                 |
| :------------ | :----------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/tank_super.xml`    | Path to the primary sprite definition file.                                 |
| `z_index`     | `-1`                                 | Determines the rendering order; lower values are rendered behind.           |

### PathFindingComponent

Controls how the entity navigates the game world.

| Attribute              | Value  | Description                                                                 |
| :--------------------- | :----- | :-------------------------------------------------------------------------- |
| `distance_to_reach_node_x` | `20`   | Horizontal distance to consider a pathfinding node reached.                 |
| `distance_to_reach_node_y` | `20`   | Vertical distance to consider a pathfinding node reached.                   |
| `frames_to_get_stuck`  | `120`  | Number of frames before the entity is considered stuck.                     |
| `can_jump`             | `0`    | The entity cannot jump.                                                     |

### CharacterPlatformingComponent

Defines movement characteristics.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `run_velocity`  | `12`  | The entity's running speed.                                                 |
| `jump_velocity_y` | `0`   | Vertical jump speed (set to 0 as `can_jump` is false).                      |

### HitboxComponent

Defines the collision boundaries for the entity.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-8`  | Minimum X-coordinate of the bounding box.                                   |
| `aabb_max_x`  | `8`   | Maximum X-coordinate of the bounding box.                                   |
| `aabb_min_y`  | `-12` | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max_y`  | `4`   | Maximum Y-coordinate of the bounding box.                                   |

### CharacterDataComponent

Provides general character data.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `mass`        | `2.4` | The mass of the character, affecting physics interactions.                  |

## Offensive Capabilities

The Tank Super has two primary attack components.

### AIAttackComponent (Ranged Machinegun)

Configures the primary ranged attack.

| Attribute                               | Value                                         | Description                                                                 |
| :-------------------------------------- | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `min_distance`                          | `30`                                          | Minimum range for this attack.                                              |
| `max_distance`                          | `500`                                         | Maximum range for this attack.                                              |
| `frames_between`                        | `3`                                           | Minimum frames between attacks.                                             |
| `frames_between_global`                 | `3`                                           | Global cooldown between attacks.                                            |
| `attack_ranged_aim_rotation_enabled`    | `1`                                           | Enables aiming rotation for ranged attacks.                                 |
| `attack_ranged_aim_rotation_speed`      | `0.05`                                        | Speed at which the entity rotates to aim.                                   |
| `attack_ranged_aim_rotation_ok_angle_deg` | `10`                                          | Maximum angle deviation allowed before stopping aiming.                     |
| `attack_ranged_root_offset_y`           | `-5`                                          | Vertical offset for the attack origin.                                      |
| `attack_ranged_offset_y`                | `-3`                                          | Vertical offset for the projectile spawn point.                             |
| `attack_ranged_offset_x`                | `10`                                          | Horizontal offset for the projectile spawn point.                           |
| `animation_name`                        | `attack_ranged`                               | The animation to play during this attack.                                   |
| `attack_ranged_entity_file`             | `data/entities/projectiles/machinegun_bullet_tank_super.xml` | The entity file for the projectile fired.                                   |
| `angular_range_deg`                     | `90`                                          | The horizontal arc within which the entity can aim.                         |

### AIAttackComponent (Grenade)

Configures the secondary grenade attack.

| Attribute                               | Value                                | Description                                                                 |
| :-------------------------------------- | :----------------------------------- | :-------------------------------------------------------------------------- |
| `min_distance`                          | `8`                                  | Minimum range for this attack.                                              |
| `max_distance`                          | `40`                                 | Maximum range for this attack.                                              |
| `frames_between`                        | `40`                                 | Minimum frames between attacks.                                             |
| `frames_between_global`                 | `40`                                 | Global cooldown between attacks.                                            |
| `attack_ranged_aim_rotation_enabled`    | `1`                                  | Enables aiming rotation for ranged attacks.                                 |
| `attack_ranged_aim_rotation_speed`      | `0.05`                               | Speed at which the entity rotates to aim.                                   |
| `attack_ranged_aim_rotation_ok_angle_deg` | `30`                                 | Maximum angle deviation allowed before stopping aiming.                     |
| `attack_ranged_root_offset_y`           | `-5`                                 | Vertical offset for the attack origin.                                      |
| `attack_ranged_offset_y`                | `-5`                                 | Vertical offset for the projectile spawn point.                             |
| `attack_ranged_offset_x`                | `3`                                  | Horizontal offset for the projectile spawn point.                           |
| `animation_name`                        | `attack_grenade`                     | The animation to play during this attack.                                   |
| `attack_ranged_entity_file`             | `data/entities/projectiles/grenade_leader.xml` | The entity file for the projectile fired.                                   |
| `attack_ranged_action_frame`            | `8`                                  | The frame within the animation when the projectile is actually fired.       |

## Visuals and Effects

### Sprite Components

The entity uses multiple sprite components for different visual elements.

*   **Main Body:** `data/enemies_gfx/tank_super.xml`
*   **Emissive:** `data/enemies_gfx/tank_super_emissive.xml` (with `emissive="1"` and `additive="1"`)
*   **Gun:** `data/enemies_gfx/tank_super_gun.xml` (with transform offsets and `z_index="-1"`)

### ExplodeOnDamageComponent

Defines what happens when the entity is destroyed.

| Attribute                   | Value                                                                 | Description                                                                 |
| :-------------------------- | :-------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| `explode_on_death_percent`  | `1`                                                                   | The entity will explode upon reaching 0 HP.                                 |
| `explode_on_damage_percent` | `0.0`                                                                 | The entity will not explode from partial damage.                            |

#### `config_explosion`

Details of the explosion effect.

| Attribute               | Value                                                                 | Description                                                                 |
| :---------------------- | :-------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| `damage`                | `3`                                                                   | Base damage of the explosion.                                               |
| `camera_shake`          | `80`                                                                  | Intensity of camera shake caused by the explosion.                          |
| `explosion_radius`      | `80`                                                                  | The radius of the explosion effect.                                         |
| `explosion_sprite`      | `data/particles/explosion_064_plasma.xml`                             | The particle effect used for the explosion visual.                          |
| `load_this_entity`      | `data/entities/particles/particle_explosion/main_green_large.xml,data/entities/misc/loose_ground.xml` | Entities to spawn upon explosion.                                           |
| `hole_destroy_liquid`   | `1`                                                                   | The explosion will destroy liquids within its radius.                       |
| `hole_enabled`          | `1`                                                                   | The explosion will create holes in terrain.                                 |
| `ray_energy`            | `240000`                                                              | Energy value for any associated ray effects.                                |
| `particle_effect`       | `1`                                                                   | Enables general particle effects for the explosion.                         |
| `damage_mortals`        | `1`                                                                   | The explosion will damage mortal entities.                                  |
| `physics_explosion_power.min` | `1.1`                                                                 | Minimum physics force applied by the explosion.                             |
| `physics_explosion_power.max` | `1.7`                                                                 | Maximum physics force applied by the explosion.                             |
| `physics_throw_enabled` | `1`                                                                   | Entities affected by the explosion will be thrown.                          |
| `spark_material`        | `spark_green`                                                         | The material of sparks generated by the explosion.                          |
| `sparks_count_min`      | `20`                                                                  | Minimum number of sparks.                                                   |
| `sparks_count_max`      | `35`                                                                  | Maximum number of sparks.                                                   |
| `stains_enabled`        | `1`                                                                   | Stains will be left by the explosion.                                       |
| `stains_radius`         | `40`                                                                  | Radius of the stains.                                                       |

## Audio Components

The entity utilizes several audio components for sound effects.

### AudioComponent

*   **File:** `data/audio/Desktop/animals.bank`
*   **Event Root:** `animals/tank`

### AudioLoopComponent (Movement)

*   **File:** `data/audio/Desktop/animals.bank`
*   **Event Name:** `animals/tank/movement_loop`
*   **Auto Play:** `1`

### AudioLoopComponent (Turret Rotate)

*   **Tags:** `turret_rotate_sound`
*   **File:** `data/audio/Desktop/animals.bank`
*   **Event Name:** `animals/tank/turret_rotate_loop`

## Special Effects

### GameEffectComponent

*   **Effect:** `PROTECTION_FREEZE`
*   **Frames:** `-1` (Indicates a permanent effect, likely for visual or functional purposes rather than a timed buff).