---
title: Physics Logo 3 Prop
category: entities
---

# Physics Logo 3 Prop

This entity defines a physics-enabled prop that appears as a logo. It's designed to interact with the game's physics engine, allowing it to fall, collide, and be affected by forces.

## Key Components and Attributes

### PhysicsImageShapeComponent

This component defines the visual representation and physical shape of the prop.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `centered`    | `1`                                 | Centers the image on the entity's origin.                                   |
| `image_file`  | `data/props_gfx/logo_3.png`         | Specifies the image file used for the prop's appearance.                  |
| `material`    | `wood_loose`                        | The material type, influencing its physical properties like friction and density. |

### PhysicsBodyComponent

This component governs the physical behavior of the entity within the physics simulation.

| Attribute              | Value | Description                                                                                             |
| :--------------------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `allow_sleep`          | `1`   | Allows the body to enter a sleep state when inactive to save performance.                               |
| `angular_damping`      | `0.01`| Reduces rotational velocity over time.                                                                  |
| `gridworld_box2d`      | `0`   | Indicates whether the physics body should be treated as part of the grid world's 2D physics.            |
| `linear_damping`       | `0.1` | Reduces linear velocity over time.                                                                      |
| `force_add_update_areas` | `1`   | Forces the entity to be added to update areas, ensuring it's processed by the physics engine.           |
| `randomize_init_velocity`| `1`   | Applies a small random initial velocity upon creation.                                                  |
| `fixed_rotation`       | `0`   | Allows the body to rotate freely.                                                                       |
| `is_bullet`            | `0`   | Not treated as a bullet, meaning it won't have special collision behavior for projectiles.              |

### PhysicsJointComponent

This component attaches the prop to a specific point, potentially with motor-driven movement.

| Attribute       | Value | Description