---
title: Rock Projectile
category: entities
---

# Rock Projectile

This document details the configuration of the Rock projectile entity in Noita, focusing on its physical properties, projectile behavior, and item representation.

## Core Components

### PhysicsBodyComponent
Manages the physical presence and movement of the rock projectile.

| Attribute           | Value      | Description                                     |
| :------------------ | :--------- | :---------------------------------------------- |
| `is_bullet`         | `1`        | Enables bullet-like physics simulation.         |
| `allow_sleep`       | `1`        | Allows the body to go to sleep when idle.       |
| `auto_clean`        | `1`        | Automatically cleans up the physics body.       |
| `linear_damping`    | `0`        | No linear damping applied.                      |
| `angular_damping`   | `0`        | No angular damping applied.                     |
| `fixed_rotation`    | `0`        | Allows rotation.                                |
| `on_death_leave_physics_body` | `0` | Does not leave a physics body on death. |

### PhysicsImageShapeComponent
Defines the visual shape and material of the projectile.

| Attribute     | Value                               | Description                               |
| :------------ | :---------------------------------- | :---------------------------------------- |
| `image_file`  | `data/projectiles_gfx/rock_projectile.png` | Sprite for the projectile.                |
| `material`    | `rock_box2d`                        | Physics material for collision.           |
| `centered`    | `1`                                 | Centers the sprite on the physics body.   |

### PhysicsThrowableComponent
Handles the throwing mechanics of the rock.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `max_throw_speed` | `80`  | Maximum speed when thrown.                |
| `throw_force_coeff` | `1.55` | Coefficient for throw force calculation. |
| `min_torque`      | `6`   | Minimum torque applied on throw.          |
| `max_torque`      | `9`   | Maximum torque applied on throw.          |

### ProjectileComponent
Governs the projectile's behavior in flight.

| Attribute         | Value | Description                                     |
| :---------------- | :---- | :---------------------------------------------- |
| `lifetime`        | `-1`  | Projectile has infinite lifetime.               |
| `penetrate_entities` | `1` | Can penetrate other entities.                   |
| `damage`          | `0.0` | Deals no direct damage.                         |
| `do_moveto_update` | `1` | Updates position based on velocity.             |

### VelocityComponent
Determines the projectile's velocity.

| Attribute             | Value | Description                               |
| :-------------------- | :---- | :---------------------------------------- |
| `affect_physics_bodies` | `1`   | Velocity affects physics bodies.          |

## Item Representation

### SpriteComponent
Defines the sprite when the rock is held in hand.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/items_gfx/in_hand/rock_in_hand.png` | Sprite for the item in hand.              |
| `_enabled`  | `0`                                 | Sprite is disabled by default.            |
| `offset_x`  | `3`                                 | X-axis offset for the sprite.             |
| `offset_y`  | `6`                                 | Y-axis offset for the sprite.             |

### UIInfoComponent
Provides information for the UI.

| Attribute | Value     | Description                 |
| :-------- | :-------- | :-------------------------- |
| `name`    | `$item_rock` | Localized name of the item. |

## Damage and Destruction

### DamageModelComponent
Manages the health and damage properties of the rock.

| Attribute                 | Value   | Description                                     |
| :------------------------ | :------ | :---------------------------------------------- |
| `hp`                      | `999.1` | High hit points, making it durable.             |
| `critical_damage_resistance` | `1`     | Has resistance to critical damage.              |
| `damage_multipliers`      | `melee="0.1"` | Reduced damage from melee attacks.            |
| `falling_damages`         | `0`     | Does not take damage from falling.              |
| `fire_damage_amount`      | `0`     | Does not take fire damage.                      |
| `ui_report_damage`        | `0`     | Damage taken is not reported in UI.             |

### ExplodeOnDamageComponent
Configures explosion behavior upon taking damage or dying.

| Attribute                         | Value | Description                                     |
| :-------------------------------- | :---- | :---------------------------------------------- |
| `explode_on_death_percent`        | `1`   | Always explodes on death.                       |
| `physics_body_modified_death_probability` | `0.9` | High probability of physics body modification on death. |
| `physics_body_destruction_required` | `0.8` | Requires 80% destruction for physics body modification. |

#### config_explosion
Details of the explosion effect.

| Attribute           | Value | Description                                     |
| :------------------ | :---- | :---------------------------------------------- |
| `damage`            | `0`   | Explosion deals no damage.                      |
| `explosion_radius`  | `0`   | Explosion has no radius.                        |
| `camera_shake`      | `0`   | No camera shake on explosion.                   |
| `particle_effect`   | `0`   | No particle effects.                            |
| `hole_enabled`      | `0`   | Does not create holes.                          |

## Audio

### AudioComponent
Defines the sound events associated with the rock projectile.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | Audio bank file.                          |
| `event_root`| `player_projectiles/throwable`      | Root event for throwable projectiles.     |

## Variables

### VariableStorageComponent
Stores custom variables for the entity.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `name`      | `projectile_file`                   | Name of the variable.                     |
| `value_string` | `data/entities/projectiles/deck/rock.xml` | The value, pointing to its own file. |