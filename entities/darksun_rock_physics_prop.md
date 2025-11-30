---
title: Darksun Rock Physics Prop
category: entities
---

# Darksun Rock Physics Prop

This entity defines a physics-enabled prop that appears as a "darksun rock". It utilizes `PhysicsBody2Component` for its physical properties and `PhysicsImageShapeComponent` to define its visual representation and material.

## Key Components

### PhysicsBody2Component

This component governs the physical behavior of the rock.

| Attribute                | Value | Description                                                                 |
| :----------------------- | :---- | :-------------------------------------------------------------------------- |
| `allow_sleep`            | `1`   | Allows the physics body to enter a sleep state when not in motion.          |
| `angular_damping`        | `0`   | No damping applied to rotational movement.                                  |
| `fixed_rotation`         | `0`   | The object's rotation is not fixed and can change.                          |
| `is_bullet`              | `0`   | This is not a projectile.                                                   |
| `linear_damping`         | `0`   | No damping applied to linear movement.                                      |
| `auto_clean`             | `0`   | The physics body will not be automatically removed.                         |
| `hax_fix_going_through_ground` | `1` | A workaround to prevent the object from falling through the ground. |

### PhysicsImageShapeComponent

This component defines the visual shape and material of the rock.

| Attribute   | Value                                 | Description                                                              |
| :---------- | :------------------------------------ | :----------------------------------------------------------------------- |
| `body_id`   | `1`                                   | Links this shape to the physics body with `uid="1"`.                     |
| `centered`  | `1`                                   | The image is centered within its physics shape.                          |
| `is_root`   | `1`                                   | This is the primary visual representation of the physics body.           |
| `image_file`| `data/items_gfx/normals_orb_40_noise.png` | The texture file used for the rock's appearance.                         |
| `material`  | `gem_box2d_darksun`                   | The physics material applied, influencing interactions with other objects. |