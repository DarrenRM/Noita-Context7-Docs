---
title: Bomb Cart Projectile
category: entities
---

# Bomb Cart Projectile

This document details the configuration of the Bomb Cart projectile entity in Noita, focusing on its core attributes and behaviors relevant to AI-assisted modding.

## Core Entity Attributes

The Bomb Cart is a projectile with several key tags defining its fundamental properties:

*   **`hittable`**: Allows the projectile to be affected by damage.
*   **`projectile`**: Identifies it as a projectile entity.
*   **`mortal`**: Indicates it can be destroyed.

## Projectile Component

This component governs the projectile's flight, lifespan, and explosion behavior.

### Key Attributes:

*   **`lifetime`**: `420` frames. The duration the projectile exists before expiring.
*   **`on_lifetime_out_explode`**: `1`. The projectile will explode when its lifetime ends.
*   **`on_death_explode`**: `1`. The projectile will explode upon being destroyed (e.g., by damage).
*   **`collide_with_world`**: `0`. The projectile does not collide with the game world geometry.
*   **`on_collision_die`**: `0`. The projectile does not die upon collision.
*   **`damage`**: `0`. The projectile itself deals no direct damage. Damage is handled by the explosion.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_launcher_large.xml`. Specifies the visual effect when the projectile is fired.
*   **`shoot_light_flash_radius`**: `120`. The radius of the light flash when fired.
*   **`shoot_light_flash_r`, `g`, `b`**: `255`, `240`, `30`. The RGB color of the light flash.

### `config_explosion` (Primary Explosion Configuration)

This nested element defines the parameters of the explosion that occurs when the projectile explodes.

| Attribute                 | Value                                                              | Description                                                                                             |
| :------------------------ | :----------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `damage`                  | `4`                                                                | The amount of damage the explosion deals.                                                               |
| `camera_shake`            | `50`                                                               | The intensity of camera shake caused by the explosion.                                                  |
| `explosion_radius`        | `40`                                                               | The radius of the explosion's effect.                                                                   |
| `explosion_sprite`        | `data/particles/explosion_040_poof.xml`                            | The visual sprite used for the explosion effect.                                                        |
| `load_this_entity`        | `data/entities/particles/particle_explosion/main_gunpowder_medium.xml,data/entities/misc/loose_ground.xml` | Entities to spawn upon explosion (e.g., particle effects, loose ground).                                |
| `create_cell_probability` | `40`                                                               | Probability (in %) of creating destructible cells within the explosion radius.                          |
| `hole_enabled`            | `1`                                                                | Whether the explosion creates holes in terrain.                                                         |
| `ray_energy`              | `6000000`                                                          | The energy of the explosion's destructive rays.                                                         |
| `damage_mortals`          | `1`                                                                | Whether the explosion damages living entities.                                                          |
| `physics_explosion_power.min` | `2.2`                                                              | Minimum force applied to physics objects in the explosion.                                              |
| `physics_explosion_power.max` | `3.6`                                                              | Maximum force applied to physics objects in the explosion.                                              |
| `physics_throw_enabled`   | `1`                                                                | Whether physics objects are thrown by the explosion.                                                    |
| `shake_vegetation`        | `1`                                                                | Whether the explosion shakes vegetation.                                                                |
| `sparks_enabled`          | `1`                                                                | Whether sparks are generated by the explosion.                                                          |
| `stains_enabled`          | `1`                                                                | Whether explosion stains are left on surfaces.                                                          |
| `stains_radius`           | `15`                                                               | The radius of the explosion stains.                                                                     |
| `max_durability_to_destroy` | `11`                                                               | The maximum durability of terrain that can be destroyed by the explosion.                               |

## ExplodeOnDamageComponent

This component allows the projectile to explode when it takes damage, in addition to its other explosion triggers.

### Key Attributes:

*   **`explode_on_death_percent`**: `1`. The projectile will explode if its durability reaches 0.
*   **`explode_on_damage_percent`**: `0.1`. The projectile has a 10% chance to explode when it takes damage.
*   **`physics_body_modified_death_probability`**: `0.9`. If the physics body is modified (e.g., deformed), there's a 90% chance it will die.
*   **`physics_body_destruction_required`**: `0.2`. The physics body needs to be at least 20% destroyed for the above probability to trigger.

### `config_explosion` (Damage Explosion Configuration)

This nested element defines the explosion parameters when triggered by damage. It shares many attributes with the primary explosion configuration.

| Attribute                 | Value                                                              | Description                                                                                             |
| :------------------------ | :----------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `damage`                  | `4`                                                                | The amount of damage the explosion deals.                                                               |
| `camera_shake`            | `50`                                                               | The intensity of camera shake caused by the explosion.                                                  |
| `explosion_radius`        | `40`                                                               | The radius of the explosion's effect.                                                                   |
| `explosion_sprite`        | `data/particles/explosion_040_poof.xml`                            | The visual sprite used for the explosion effect.                                                        |
| `load_this_entity`        | `data/entities/particles/particle_explosion/main_gunpowder_medium.xml,data/entities/misc/loose_ground.xml` | Entities to spawn upon explosion (e.g., particle effects, loose ground).                                |
| `create_cell_probability` | `40`                                                               | Probability (in %) of creating destructible cells within the explosion radius.                          |
| `hole_enabled`            | `1`                                                                | Whether the explosion creates holes in terrain.                                                         |
| `ray_energy`              | `6000000`                                                          | The energy of the explosion's destructive rays.                                                         |
| `damage_mortals`          | `1`                                                                | Whether the explosion damages living entities.                                                          |
| `physics_explosion_power.min` | `2.2`                                                              | Minimum force applied to physics objects in the explosion.                                              |
| `physics_explosion_power.max` | `3.6`                                                              | Maximum force applied to physics objects in the explosion.                                              |
| `physics_throw_enabled`   | `1`                                                                | Whether physics objects are thrown by the explosion.                                                    |
| `shake_vegetation`        | `1`                                                                | Whether the explosion shakes vegetation.                                                                |
| `sparks_enabled`          | `1`                                                                | Whether sparks are generated by the explosion.                                                          |
| `stains_enabled`          | `1`                                                                | Whether explosion stains are left on surfaces.                                                          |
| `stains_radius`           | `15`                                                               | The radius of the explosion stains.                                                                     |
| `max_durability_to_destroy` | `11`                                                               | The maximum durability of terrain that can be destroyed by the explosion.                               |
| `audio_event_name`        | `explosions/cart`                                                  | The audio event triggered by this explosion.                                                            |

## Physics Components

These components define the physical properties and appearance of the Bomb Cart.

### `PhysicsBody2Component`

*   **`allow_sleep`**: `1`. Allows the physics body to enter a sleep state when inactive.
*   **`linear_damping`**: `0.25`. Resistance to linear motion.
*   **`angular_damping`**: `0.4`. Resistance to rotational motion.
*   **`root_offset_x`, `root_offset_y`**: `9`, `7`. Offset for the physics body's root.

### `PhysicsImageShapeComponent` (Main Body)

*   **`body_id`**: `1`. Identifies this as the primary physics body.
*   **`is_root`**: `1`. This shape is the root of the physics body.
*   **`offset_x`, `offset_y`**: `-7`, `-15`. Offset for the sprite.
*   **`image_file`**: `data/projectiles_gfx/bomb_cart.png`. The main sprite for the bomb cart.
*   **`material`**: `metal_rust`. The material properties of this shape.

### `PhysicsImageShapeComponent` (Wheels)

Two instances of this component define the wheels.

*   **`body_id`**: `2` and `3`. Separate physics bodies for each wheel.
*   **`is_circle`**: `1`. Defines the shape as a circle.
*   **`offset_x`, `offset_y`**: `-9`, `-15`. Offset for the wheel sprites.
*   **`image_file`**: `data/projectiles_gfx/bomb_cart_wheel_left.png` and `data/projectiles_gfx/bomb_cart_wheel_right.png`. Sprites for the left and right wheels.
*   **`z`**: `-1`. Renders the wheels behind the main body.
*   **`material`**: `metal_prop_loose`. Material properties for the wheels.

### `PhysicsJoint2MutatorComponent` (x2)

These components configure the motors for the revolute joints connecting the wheels to the body.

*   **`joint_id`**: `1` and `2`. Identifies the joint being configured.
*   **`motor_speed`**: `0`. The target speed of the motor.
*   **`motor_max_torque`**: `20`. The maximum torque the motor can apply.

### `PhysicsJoint2Component` (x2)

These components define the revolute joints that attach the wheels to the main body.

*   **`type`**: `REVOLUTE_JOINT`. The type of joint.
*   **`joint_id`**: `1` and `2`. Identifies the joint.
*   **`break_force`**: `20`. The force at which the joint will break.
*   **`body1_id`**: `1`. The ID of the first connected body (the main cart body).
*   **`body2_id`**: `2` or `3`. The ID of the second connected body (the respective wheel).
*   **`offset_x`, `offset_y`**: Defines the connection point relative to the bodies.

## Variable Storage Component

*   **`name`**: `reverse`, **`value_bool`**: `0`. A boolean variable, likely used by scripts to control direction.
*   **`name`**: `projectile_file`, **`value_string`**: `data/entities/projectiles/bomb_cart.xml`. Stores the path to this entity's XML file.

## Lua Components

These components execute custom Lua scripts to control the Bomb Cart's behavior.

*   **`script_source_file`**: `data/scripts/projectiles/bomb_cart_init.lua`.
    *   **`execute_every_n_frame`**: `1`.
    *   **`execute_times`**: `1`. This script runs once at the beginning to initialize the bomb cart.
*   **`script_source_file`**: `data/scripts/projectiles/bomb_cart.lua`.
    *   **`execute_every_n_frame`**: `1`. This script runs every frame to manage the bomb cart's ongoing behavior.

## Particle Emitters

These components generate visual effects.

### Smoke Emitter

*   **`emitted_material_name`**: `smoke`.
*   Generates small, short-lived smoke particles.

### Spark Emitters (x2)

*   **`emitted_material_name`**: `spark`.
*   One emitter generates cosmetic sparks, the other real particles.
*   The second emitter is sparse and generates longer-lasting sparks with gravity and airflow effects.

## Audio Components

*   **`AudioComponent`**:
    *   **`file`**: `data/audio/Desktop/projectiles.bank`.
    *   **`event_root`**: `player_projectiles/bomb_cart`. Defines the base audio event for the projectile.
*   **`AudioLoopComponent`**:
    *   **`file`**: `data/audio/Desktop/projectiles.bank`.
    *   **`event_name`**: `projectiles/fuse_burn_slow`.
    *   **`auto_play`**: `1`. Plays a continuous fuse burning sound.