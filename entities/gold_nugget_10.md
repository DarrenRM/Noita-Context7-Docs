---
title: Gold Nugget (10)
category: entities
---

# Gold Nugget (10)

This document details the `goldnugget_10.xml` entity, representing a small gold nugget pickup in Noita.

## Core Components

This entity is primarily defined by its physical properties, item-related attributes, and visual effects.

### `PhysicsBodyComponent`

Handles the physical behavior of the gold nugget in the game world.

| Attribute           | Value | Description                                      |
| :------------------ | :---- | :----------------------------------------------- |
| `allow_sleep`       | `1`   | Allows the physics body to sleep when inactive.  |
| `angular_damping`   | `0`   | No angular damping applied.                      |
| `fixed_rotation`    | `0`   | Allows rotation.                                 |
| `linear_damping`    | `0`   | No linear damping applied.                       |
| `hax_fix_going_through_ground` | `1` | A fix to prevent the object from falling through the ground. |
| `on_death_leave_physics_body` | `1` | The physics body persists even if the entity is destroyed. |

### `PhysicsImageShapeComponent`

Defines the visual shape and material of the gold nugget.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `body_id`   | `1`                                 | Links to the `PhysicsBodyComponent`.      |
| `centered`  | `1`                                 | Centers the image on its origin.          |
| `image_file`| `data/items_gfx/goldnugget_6px.png` | The sprite used for the gold nugget.      |
| `material`  | `gold_box2d`                        | The physics material, likely affecting interactions. |

### `VariableStorageComponent`

Stores custom variables associated with the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `name`    | `gold_value` | The name of the variable.                 |
| `value_int`| `10`  | The integer value, representing 10 gold. |

### `ItemComponent`

Defines the item's properties and how it behaves as a pickup.

| Attribute                 | Value | Description                                      |
| :------------------------ | :---- | :----------------------------------------------- |
| `auto_pickup`             | `1`   | The item is automatically picked up when close.  |
| `item_name`               | `$item_goldnugget_10` | The internal name for the item.              |
| `stats_count_as_item_pick_up` | `0`   | This pickup does not count towards item pickup stats. |
| `is_pickable`             | `1`   | The item can be picked up.                       |
| `preferred_inventory`     | `FULL`| Suggests the full inventory for pickup.          |

### `HitboxComponent`

Defines the collision area of the gold nugget.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-3`  | Minimum X-axis bounding box coordinate.   |
| `aabb_max_x`| `3`   | Maximum X-axis bounding box coordinate.   |
| `aabb_min_y`| `-5`  | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_y`| `0`   | Maximum Y-axis bounding box coordinate.   |

### `LifetimeComponent`

Determines how long the gold nugget persists in the world.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `900` | The entity will disappear after 900 frames. |

## Scripting and Effects

This section covers the scripts and particle effects attached to the gold nugget.

### `LuaComponent` (Item Pickup)

This component links to a script that handles the logic when the item is picked up.

| Attribute             | Value                                | Description                               |
| :-------------------- | :----------------------------------- | :---------------------------------------- |
| `script_item_picked_up` | `data/scripts/items/gold_pickup.lua` | The script executed when the item is picked up. |

### `LuaComponent` (Gold Explosion)

This component executes a script upon the entity's addition, likely for an initial effect.

| Attribute           | Value                                | Description                               |
| :------------------ | :----------------------------------- | :---------------------------------------- |
| `script_source_file`| `data/scripts/perks/gold_explosion.lua` | The script to execute.                    |
| `execute_on_added`  | `1`                                  | The script runs when the entity is added. |
| `remove_after_executed` | `1`                              | The script component is removed after execution. |

### `SpriteParticleEmitterComponent` (Particle Glitter)

This component generates a particle effect to simulate glitter or shine.

| Attribute                 | Value   | Description                                      |
| :------------------------ | :------ | :----------------------------------------------- |
| `sprite_file`             | `data/particles/shine_08.xml` | The particle sprite definition.                  |
| `lifetime`                | `0.2`   | Duration of each particle.                       |
| `emission_interval_min_frames` | `50`    | Minimum frames between particle emissions.       |
| `emission_interval_max_frames` | `250`   | Maximum frames between particle emissions.       |
| `count_min`               | `1`     | Minimum particles emitted per interval.          |
| `count_max`               | `1`     | Maximum particles emitted per interval.          |
| `additive`                | `1`     | Particles use additive blending.                 |
| `scale.x`                 | `1.0`   | Base X scale of particles.                       |
| `scale.y`                 | `1.0`   | Base Y scale of particles.                       |
| `sprite_random_rotation`  | `1`     | Particles have random rotation.                  |
| `randomize_scale.min_x`   | `-0.1`  | Minimum random X scale variation.                |
| `randomize_scale.max_x`   | `0.1`   | Maximum random X scale variation.                |
| `randomize_position.min_y`| `-3`    | Minimum random Y position offset.                |
| `randomize_position.max_y`| `3`     | Maximum random Y position offset.                |
| `velocity_slowdown`       | `6`     | How quickly particles slow down.                 |
| `randomize_animation_speed_coeff.min` | `0.667` | Minimum random animation speed multiplier. |
| `randomize_animation_speed_coeff.max` | `1.0`   | Maximum random animation speed multiplier. |