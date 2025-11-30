---
title: Tank Entity Documentation
category: entities
---

# Tank Entity Documentation

This document details the `tank.xml` entity, a robotic enemy found in Noita. It focuses on key attributes relevant for AI-assisted modding.

## Core Attributes

The Tank entity inherits from `base_enemy_robot.xml` and possesses several defining characteristics:

### `AnimalAIComponent`

This component governs the Tank's behavior and combat capabilities.

| Attribute                       | Value      | Description                                                                 |
| :------------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault` | The default job assigned to this AI.                                        |
| `escape_if_damaged_probability` | `0`        | The probability of escaping when damaged (0 means it never flees).          |
| `attack_melee_damage_min`       | `0.4`      | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | `0.7`      | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`    | `600`      | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `600`      | Vertical range for detecting creatures.                                     |
| `attack_ranged_min_distance`    | `0`        | Minimum distance for ranged attacks.                                        |
| `attack_ranged_max_distance`    | `500`      | Maximum distance for ranged attacks.                                        |
| `food_material`                 | `blood`    | The material this creature considers food (though `needs_food` is 0).       |
| `needs_food`                    | `0`        | Whether the creature requires food to survive (0 means it does not).        |
| `sense_creatures`               | `1`        | Whether the creature can sense other creatures.                             |
| `attack_melee_enabled`          | `0`        | Whether melee attacks are enabled (0 means disabled).                       |
| `can_fly`                       | `0`        | Whether the creature can fly (0 means it cannot).                           |
| `aggressiveness_min`            | `1`        | Minimum aggressiveness level.                                               |
| `aggressiveness_max`            | `95`       | Maximum aggressiveness level.                                               |

### `DamageModelComponent`

Defines the Tank's health, resistances, and how it takes damage.

| Attribute                       | Value      | Description                                                                 |
| :------------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `hp`                            | `4.5`      | Hit points of the Tank.                                                     |
| `ragdoll_material`              | `steel`    | The material used for its ragdoll when defeated.                            |
| `blood_material`                | `oil`      | The material that spills out when damaged (acts as "blood").                |
| `fire_probability_of_ignition`  | `0`        | Probability of igniting from fire damage.                                   |
| `in_liquid_shooting_electrify_prob` | `30`       | Probability of electrifying when shooting in liquid.                        |

#### `damage_multipliers`

Specific multipliers for different damage types.

| Damage Type | Multiplier | Description                               |
| :---------- | :--------- | :---------------------------------------- |
| `projectile`| `0.5`      | Reduced damage from projectiles.          |
| `explosion` | `1.1`      | Increased damage from explosions.         |
| `electricity`| `2`        | Increased damage from electricity.        |
| `fire`      | `0.1`      | Significantly reduced damage from fire.   |

### `SpriteComponent`

Controls the visual representation of the Tank.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/tank.xml`         | The primary sprite file for the Tank's body.                                |
| `z_index`     | `-1`                                | Controls rendering order; -1 places it behind most other entities.          |

### `PathFindingComponent`

Defines how the Tank navigates the game world.

| Attribute                 | Value | Description                                                                 |
| :------------------------ | :---- | :-------------------------------------------------------------------------- |
| `distance_to_reach_node_x`| `20`  | Horizontal distance to consider a pathfinding node reached.                 |
| `distance_to_reach_node_y`| `20`  | Vertical distance to consider a pathfinding node reached.                   |
| `frames_to_get_stuck`     | `120` | Number of frames before the AI is considered stuck.                         |
| `can_jump`                | `0`   | Whether the AI can jump (0 means it cannot).                                |

### `CharacterPlatformingComponent`

Governs movement and physics related to platforming.

| Attribute         | Value | Description                                                                 |
| :---------------- | :---- | :-------------------------------------------------------------------------- |
| `run_velocity`    | `12`  | The horizontal movement speed of the Tank.                                  |
| `jump_velocity_y` | `0`   | Vertical velocity when jumping (0 means it cannot jump).                    |

### `HitboxComponent`

Defines the collision boundaries for the Tank.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `aabb_min_x`  | `-8`  | Minimum X-coordinate of the bounding box.                                   |
| `aabb_max_x`  | `8`   | Maximum X-coordinate of the bounding box.                                   |
| `aabb_min_y`  | `-12` | Minimum Y-coordinate of the bounding box.                                   |
| `aabb_max_y`  | `4`   | Maximum Y-coordinate of the bounding box.                                   |

## Combat Components

The Tank has specialized components for its offensive capabilities.

### `ExplodeOnDamageComponent`

Determines if and how the Tank explodes when damaged or defeated.

| Attribute                     | Value | Description                                                                 |
| :---------------------------- | :---- | :-------------------------------------------------------------------------- |
| `explode_on_death_percent`    | `1`   | The Tank will explode upon death.                                           |
| `explode_on_damage_percent`   | `0.0` | The Tank will not explode from partial damage.                              |

#### `config_explosion`

Details of the explosion effect.

| Attribute                   | Value   | Description                                                                 |
| :-------------------------- | :------ | :-------------------------------------------------------------------------- |
| `damage`                    | `3`     | Base damage of the explosion.                                               |
| `camera_shake`              | `40`    | Intensity of camera shake caused by the explosion.                          |
| `explosion_radius`          | `40`    | The radius of the explosion effect.                                         |
| `explosion_sprite`          | `...`   | Path to the particle effect used for the explosion.                         |
| `create_cell_probability`   | `70`    | Probability of creating terrain cells (e.g., holes).                        |
| `hole_enabled`              | `1`     | Whether the explosion can create holes in terrain.                          |
| `ray_energy`                | `180000`| Energy of the explosion's damaging rays.                                    |
| `damage_mortals`            | `1`     | Whether the explosion damages mortal entities.                              |
| `physics_explosion_power.min`| `1.1`   | Minimum physics force applied to entities by the explosion.                 |
| `physics_explosion_power.max`| `1.7`   | Maximum physics force applied to entities by the explosion.                 |
| `sparks_enabled`            | `1`     | Whether sparks are generated by the explosion.                              |
| `stains_enabled`            | `1`     | Whether damage stains are created by the explosion.                         |

### `AIAttackComponent` (Ranged - Machinegun)

Configuration for the Tank's primary ranged attack.

| Attribute                           | Value   | Description                                                                 |
| :---------------------------------- | :------ | :-------------------------------------------------------------------------- |
| `min_distance`                      | `30`    | Minimum distance for this attack.                                           |
| `max_distance`                      | `500`   | Maximum distance for this attack.                                           |
| `frames_between`                    | `3`     | Frames between attacks.                                                     |
| `attack_ranged_aim_rotation_speed`  | `0.05`  | Speed at which the turret aims.                                             |
| `attack_ranged_entity_file`         | `...`   | Path to the projectile entity file (`machinegun_bullet_tank.xml`).          |
| `angular_range_deg`                 | `90`    | The horizontal arc the turret can aim within.                               |

### `AIAttackComponent` (Ranged - Grenade)

Configuration for the Tank's secondary ranged attack (grenade).

| Attribute                           | Value   | Description                                                                 |
| :---------------------------------- | :------ | :-------------------------------------------------------------------------- |
| `min_distance`                      | `8`     | Minimum distance for this attack.                                           |
| `max_distance`                      | `40`    | Maximum distance for this attack.                                           |
| `frames_between`                    | `40`    | Frames between grenade attacks.                                             |
| `attack_ranged_entity_file`         | `...`   | Path to the projectile entity file (`grenade_scavenger.xml`).               |
| `attack_ranged_action_frame`        | `8`     | The frame within the animation where the attack is executed.                |

## Visual Components

Additional sprites for emissive effects and the gun.

### `SpriteComponent` (`_tags="character"`)

Handles the emissive visual effects.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/tank_emissive.xml`| Sprite file for emissive effects.                                           |
| `emissive`    | `1`                                 | Enables emissive rendering.                                                 |
| `additive`    | `1`                                 | Uses additive blending for the emissive effect.                             |
| `rect_animation`| `walk`                              | Specifies the animation to use for walking.                                 |

### `SpriteComponent` (`_tags="gun"`)

Renders the Tank's gun.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`  | `data/enemies_gfx/tank_gun.xml`     | Sprite file for the gun.                                                    |
| `transform_offset.y`| `-5`                                | Offsets the gun's position vertically.                                      |
| `update_transform`| `1`                                 | Enables transform updates (e.g., rotation).                               |
| `z_index`     | `-1`                                | Places the gun behind the main body.                                        |

## Audio Components

Defines the sound effects associated with the Tank.

### `AudioComponent`

General sound bank and event root.

| Attribute   | Value                     | Description                                                                 |
| :---------- | :------------------------ | :-------------------------------------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank` | The audio bank file.                                                        |
| `event_root`| `animals/tank`            | The root event path for Tank sounds.                                        |

### `AudioLoopComponent` (Movement)

Handles looping movement sounds.

| Attribute                                | Value | Description                                                                 |
| :--------------------------------------- | :---- | :-------------------------------------------------------------------------- |
| `event_name`                             | `...` | The specific event for movement loop (`animals/tank/movement_loop`).        |
| `set_speed_parameter_only_based_on_x_movement` | `1`   | Speed parameter is solely based on horizontal movement.                     |
| `auto_play`                              | `1`   | The sound loop starts automatically.                                        |

### `AudioLoopComponent` (Turret Rotate)

Handles looping sounds for turret rotation.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `event_name`| `animals/tank/turret_rotate_loop`   | The specific event for turret rotation loop.                                |
| `volume_autofade_speed` | `0.1`                               | Controls how quickly the volume fades in/out.                               |

## Special Effects

### Protection from Freezing

The Tank has an inherent immunity to freezing effects.

```xml
	<Entity>
		<InheritTransformComponent />
		
	    <GameEffectComponent 
	        effect="PROTECTION_FREEZE"
	        frames="-1"
	    >
		</GameEffectComponent >
	</Entity>
```