---
title: Contact Damage Entity
category: entities
---

# Contact Damage Entity

This entity defines a basic area of effect that deals damage to specific entities upon contact. It's often used for passive damage effects or as a component for other entities.

## Key Components and Attributes

### `AreaDamageComponent`

This component is responsible for applying damage within a defined area.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `aabb_min.x`     | Minimum X-coordinate of the damage area's bounding box.                     |
| `aabb_min.y`     | Minimum Y-coordinate of the damage area's bounding box.                     |
| `aabb_max.x`     | Maximum X-coordinate of the damage area's bounding box.                     |
| `aabb_max.y`     | Maximum Y-coordinate of the damage area's bounding box.                     |
| `damage_per_frame` | The amount of damage dealt per frame to entities within the area.           |
| `update_every_n_frame` | How often (in frames) the damage check and application occurs.            |
| `entities_with_tag` | A comma-separated list of entity tags that will be affected by the damage. |
| `damage_type`    | The type of damage being dealt (e.g., `DAMAGE_MELEE`, `DAMAGE_PROJECTILE`). |

### `LuaComponent`

Allows for custom Lua scripting to extend or modify the entity's behavior.

| Attribute         | Description                                                              |
| :---------------- | :----------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script file that will be executed.                       |
| `execute_every_n_frame` | How often (in frames) the Lua script will be executed.                   |

### `SpriteComponent`

Defines the visual representation of the entity.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `image_file`    | The image file used for the sprite.                                      |
| `offset_x`      | Horizontal offset of the sprite relative to the entity's origin.         |
| `offset_y`      | Vertical offset of the sprite relative to the entity's origin.           |
| `z_index`       | Determines the rendering order of the sprite.                            |
| `rect_animation` | Specifies the name of the rectangle animation to play.                   |

### `LifetimeComponent`

Controls how long the entity exists before being removed.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The duration (in frames) the entity lasts. |

### `InheritTransformComponent`

Allows the entity to inherit the transform (position, rotation, scale) of its parent.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `use_root_parent` | If set to `1`, it inherits transform from the root parent.               |

## Example Usage

This entity, when placed in the game world, will create a small, purple, pulsating area that deals 0.14 damage per frame to any entity tagged as "enemy" within its 32x32 pixel bounding box. The visual indicator is a purple circle, and the damage effect is tied to a Lua script for potential further customization. The entity will persist for 1200 frames (approximately 20 seconds).