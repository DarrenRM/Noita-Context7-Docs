---
title: Debug Physics Wand
category: entities
---

---

# Debug Physics Wand

This document describes the `physics_wand.xml` entity, which appears to be a debug entity for testing physics interactions in Noita.

## Core Components

This entity utilizes several core Noita components to define its physical presence and visual representation.

### PhysicsBodyComponent

This component defines the physical properties of the entity.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `_tags`                   | `enabled_in_world`: The entity is active when in the game world.                                        |
| `uid`                     | Unique identifier for the component.                                                                    |
| `allow_sleep`             | `1`: Allows the physics body to enter a sleep state when inactive to save performance.                  |
| `angular_damping`         | `0`: No rotational friction.                                                                            |
| `fixed_rotation`          | `0`: The entity's rotation can change.                                                                  |
| `is_bullet`               | `1`: The entity behaves like a projectile.                                                              |
| `linear_damping`          | `0`: No linear friction.                                                                                |
| `auto_clean`              | `0`: The entity does not automatically clean itself up.                                                 |
| `on_death_leave_physics_body` | `0`: Does not leave a physics body behind when destroyed.                                               |
| `hax_fix_going_through_ground` | `1`: A hack to prevent the entity from falling through the ground.                                     |
| `hax_fix_going_through_sand` | `0`: Does not have a specific fix for going through sand.                                               |
| `hax_wait_till_pixel_scenes_loaded` | `1`: Waits for pixel scenes to load before becoming fully active.                                   |
| `force_add_update_areas`  | `1`: Forces the addition of update areas for this entity.                                               |

### PhysicsShapeComponent

Defines the collision shape of the entity.

| Attribute         | Description                                                                                             |
| :---------------- | :------------------------------------------------------------------------------------------------------ |
| `is_circle`       | `0`: The shape is not a circle.                                                                         |
| `is_box`          | `1`: The shape is a box.                                                                                |
| `radius_x`        | `6`: The half-width of the box collider.                                                                |
| `radius_y`        | `2.5`: The half-height of the box collider.                                                             |
| `friction`        | `0.35`: The amount of friction applied when colliding with other surfaces.                              |
| `restitution`     | `0.15`: The bounciness of the entity upon collision.                                                    |
| `local_position_x`| `3.0`: The X-offset of the shape relative to the entity's origin.                                       |
| `local_position_y`| `0.0`: The Y-offset of the shape relative to the entity's origin.                                       |

### SpriteComponent

Determines the visual appearance of the entity.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `_enabled`            | `1`: The sprite is enabled.                                                                             |
| `_tags`               | `enabled_in_hand`, `enabled_in_world`, `item`: Tags indicating where and how the sprite is displayed. |
| `image_file`          | `data/items_gfx/handgun.xml`: Specifies the graphical asset used for the sprite.                        |
| `z_index`             | `-1.5`: Controls the rendering order of the sprite.                                                     |
| `update_transform`    | `1`: The sprite's transform (position, rotation, scale) is updated.                                     |
| `update_transform_rotation` | `1`: The sprite's rotation is updated.                                                              |
| `visible`             | `1`: The sprite is visible.                                                                             |

### UIInfoComponent

Provides information for the user interface.

| Attribute | Description                                                                                             |
| :-------- | :------------------------------------------------------------------------------------------------------ |
| `_tags`   | `enabled_in_world`: The UI info is active when in the game world.                                       |
| `name`    | `Throwing knife`: The name displayed in the UI.                                                         |