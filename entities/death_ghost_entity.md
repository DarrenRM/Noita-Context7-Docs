---
title: Death Ghost Entity
category: entities
---

# Death Ghost Entity

This document describes the `death_ghost.xml` entity, which represents the "Death Ghost" in Noita. This entity is a passive, damaging entity that appears under specific conditions.

## Core Components

The Death Ghost entity is built upon several key components that define its behavior and appearance.

### HitboxComponent
Defines the physical boundaries of the entity.

| Attribute   | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `aabb_min_x`| `-4`    | Minimum X-axis bounding box coordinate.   |
| `aabb_max_x`| `4`     | Maximum X-axis bounding box coordinate.   |
| `aabb_min_y`| `-4`    | Minimum Y-axis bounding box coordinate.   |
| `aabb_max_y`| `4`     | Maximum Y-axis bounding box coordinate.   |

### SimplePhysicsComponent
Enables basic physics interactions for the entity.

### VelocityComponent
Controls the movement and velocity of the entity.

| Attribute  | Value | Description                               |
| :--------- | :---- | :---------------------------------------- |
| `gravity_y`| `0`   | Disables vertical gravity for the entity. |

### AreaDamageComponent
Handles the damage dealt by the entity to other entities within its area of effect.

| Attribute         | Value           | Description                                                              |
| :---------------- | :-------------- | :----------------------------------------------------------------------- |
| `aabb_min.x`      | `-8`            | Minimum X-axis bounding box for damage area.                             |
| `aabb_min.y`      | `-8`            | Minimum Y-axis bounding box for damage area.                             |
| `aabb_max.x`      | `8`             | Maximum X-axis bounding box for damage area.                             |
| `aabb_max.y`      | `8`             | Maximum Y-axis bounding box for damage area.                             |
| `damage_per_frame`| `0.07`          | Amount of damage dealt per frame.                                        |
| `update_every_n_frame`| `1`             | How often the damage is applied (every frame in this case).              |
| `entities_with_tag`| `homing_target` | Only applies damage to entities with the "homing_target" tag.            |
| `damage_type`     | `DAMAGE_CURSE`  | The type of damage dealt, which is curse damage.                         |

### SpriteComponent
Defines the visual representation of the Death Ghost.

| Attribute    | Value                           | Description                               |
| :----------- | :------------------------------ | :---------------------------------------- |
| `image_file` | `data/projectiles_gfx/death_ghost.xml` | Path to the sprite's graphical definition. |

### LuaComponent
Attaches a Lua script to control the entity's behavior.

| Attribute           | Value                                | Description                                                              |
| :------------------ | :----------------------------------- | :----------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/animals/death_ghost_move.lua` | Path to the Lua script that governs the ghost's movement and logic.      |
| `execute_every_n_frame`| `1`                                  | How often the Lua script is executed (every frame).                      |

### AudioComponent & AudioLoopComponent
Handle sound effects for the entity.

| Attribute     | Value                               | Description                                                              |
| :------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `file`        | `data/audio/Desktop/animals.bank`   | The audio bank containing the sound events.                              |
| `event_root`  | `animals/tiny_ghost`                | The root event name for general sounds.                                  |
| `event_name`  | `animals/tiny_ghost/movement_loop`  | The specific event name for the movement loop.                           |
| `set_speed_parameter`| `1`                                 | Controls if the movement loop speed is tied to the entity's speed.       |
| `auto_play`   | `1`                                 | The audio loop starts automatically when the entity is spawned.          |

### CameraBoundComponent
Manages how the entity interacts with the camera's view.

| Attribute   | Value | Description                                                              |
| :---------- | :---- | :----------------------------------------------------------------------- |
| `max_count` | `20`  | Maximum number of this entity that can be active within camera bounds.   |
| `distance`  | `2000`| The radius around the camera within which this entity can exist.         |

### LifetimeComponent
Determines how long the entity will exist before despawning.

| Attribute | Value  | Description                               |
| :-------- | :----- | :---------------------------------------- |
| `lifetime`| `1800` | The lifespan of the entity in frames.     |