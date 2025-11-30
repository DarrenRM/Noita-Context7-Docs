---
title: Sun Rock Physics Properties
category: entities
---

# Sun Rock Physics Properties

This document details the physics properties of the "Sun Rock" entity in Noita, useful for AI-assisted modding.

## Entity Definition

The `physics_sun_rock.xml` file defines an entity with the tag `sunrock`.

## Key Components and Attributes

### PhysicsBody2Component

This component governs the physical behavior of the entity.

| Attribute        | Value | Description                                                              |
| :--------------- | :---- | :----------------------------------------------------------------------- |
| `allow_sleep`    | `1`   | Allows the physics body to enter a sleep state when inactive.            |
| `angular_damping`| `0`   | No angular damping applied, allowing free rotation.                      |
| `fixed_rotation` | `0`   | Rotation is not fixed, allowing the object to spin.                      |
| `is_bullet`      | `0`   | Not treated as a bullet; it's a solid object.                            |
| `linear_damping` | `0`   | No linear damping applied, allowing free movement.                       |
| `auto_clean`     | `0`   | The entity will not be automatically cleaned up by the game.             |
| `hax_fix_going_through_ground` | `1` | A specific fix to prevent the object from clipping through the ground. |

### PhysicsImageShapeComponent

This component defines the visual shape and collision properties based on an image.

| Attribute | Value                                     | Description                                                              |
| :-------- | :---------------------------------------- | :----------------------------------------------------------------------- |
| `body_id` | `1`                                       | Refers to the physics body this shape is attached to.                    |
| `centered`| `1`                                       | The image is centered on the physics body's origin.                      |
| `is_root` | `1`                                       | This shape is the root shape for the physics body.                       |
| `image_file` | `data/items_gfx/normals_orb_40_noise.png` | The image file used to define the shape and texture.                     |
| `material`| `gem_box2d_yellow_sun_gravity`            | The physics material applied, influencing interactions and properties. |