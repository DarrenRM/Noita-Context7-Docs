---
title: Racing Cart Entity
category: entities
---

# Racing Cart Entity

This document describes the `racing_cart.xml` entity, which defines the behavior and appearance of the racing cart in Noita.

## Core Components

The racing cart is built upon several key components that dictate its movement, interaction, and visual representation.

### VelocityComponent

Controls the cart's movement physics.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `gravity_y`    | Set to `0` to disable vertical gravity.         |
| `air_friction` | Controls air resistance affecting movement.      |
| `terminal_velocity` | Maximum falling speed.                          |

### ProjectileComponent

Enables the cart to interact with the game world as a projectile, allowing it to bounce and collide.

| Attribute             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| `speed_min`, `speed_max` | Set to `0` as the cart's movement is controlled by Lua scripts.          |
| `bounce_always`       | Set to `1` to ensure the cart always bounces.                            |
| `bounces_left`        | Set to a very high number for effectively infinite bounces.              |
| `bounce_at_any_angle` | Set to `1` to allow bouncing regardless of the impact angle.             |
| `bounce_energy`       | Controls how much velocity is retained after a bounce (0.5 means half).  |
| `penetrate_entities`  | Set to `1` to allow the cart to pass through other entities.             |
| `collide_with_tag`    | Specifies the tag of entities the cart should collide with (e.g., "racing_track"). |

### SpriteComponent

Defines the visual appearance of the cart.

| Tag         | Image File                                  | Description                                                              |
|-------------|---------------------------------------------|--------------------------------------------------------------------------|
| `driverless` | `data/projectiles_gfx/racing_cart.xml`      | The default sprite for the cart when no driver is present.               |
| `driver`    | `data/projectiles_gfx/racing_cart_killer.xml` | A sprite for the cart when it's in a "killer" state (likely with a driver). |
| `has_special_scale` | `1`                                         | Indicates that special scaling is applied to the sprite.                 |
| `special_scale_x` | `1`                                         | The specific X-axis scaling factor.                                      |

## Movement and Logic

Lua scripts are used to manage the cart's dynamic behavior.

### LuaComponent

| Script File                                     | Execute Every N Frame | Description                                                                                             |
|-------------------------------------------------|-----------------------|---------------------------------------------------------------------------------------------------------|
| `data/scripts/buildings/racing_cart_move.lua`   | `1`                   | Handles the primary movement logic of the racing cart.                                                  |
| `data/scripts/buildings/racing_cart_check.lua`  | `20`                  | Used for driverless carts, likely for checking race conditions or pathfinding.                          |
| `data/scripts/buildings/racing_cart_checkpoint.lua` | `-1`                  | Executed when the `CollisionTriggerComponent` hits a checkpoint, managing race progress and timing. |

## Race Logic and Checkpoints

Components related to race tracking and checkpoint management.

### CollisionTriggerComponent

Detects collisions with specific entities to trigger race events.

| Attribute              | Description                                                              |
|------------------------|--------------------------------------------------------------------------|
| `required_tag`         | The tag of entities that will trigger this component (e.g., "racing_checkpoint"). |
| `width`, `height`, `radius` | Defines the collision detection area.                                    |
| `destroy_this_entity_when_triggered` | Set to `0` to prevent the cart from being destroyed upon triggering. |

### VariableStorageComponent

Stores variables for tracking race progress and best times.

| Name           | Type    | Initial Value | Description                                     |
|----------------|---------|---------------|-------------------------------------------------|
| `lap_start_time` | `int`   | `0`           | Stores the time when a lap begins.              |
| `best_time`    | `int`   | `99999999`    | Stores the fastest lap time achieved.           |
| `checkpoint_1` | `bool`  | `0`           | Flag to indicate if checkpoint 1 has been passed. |
| `checkpoint_2` | `bool`  | `0`           | Flag to indicate if checkpoint 2 has been passed. |

## Visual Effects and Audio

Components for visual flair and sound.

### LightComponent

Adds a light source to the cart.

| Attribute | Description                               |
|-----------|-------------------------------------------|
| `radius`  | The radius of the light emitted by the cart. |

### ParticleEmitterComponent

Generates various particle effects.

| Attribute                 | Description