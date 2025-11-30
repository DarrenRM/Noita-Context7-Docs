---
title: Physics Cart Entity
category: entities
---

# Physics Cart Entity

This document describes the `physics_cart.xml` entity, which represents a physics-driven cart object in Noita. It's composed of multiple physics bodies and joints to simulate realistic movement.

## Key Components

### `PhysicsBodyComponent`

This component defines the physical properties of a rigid body. The cart uses two `PhysicsBodyComponent` instances:

*   **Body 1 (Cart Body):**
    *   `uid`: `1`
    *   `allow_sleep`: `1` (Allows the body to go to sleep when inactive to save performance)
    *   `fixed_rotation`: `0` (Allows rotation)
    *   `on_death_leave_physics_body`: `1` (The physics body persists after the entity dies)

*   **Body 2 (Wheel Body):**
    *   `uid`: `2`
    *   `allow_sleep`: `1`
    *   `angular_damping`: `0.1` (Reduces rotational velocity over time)
    *   `fixed_rotation`: `0`
    *   `on_death_leave_physics_body`: `1`
    *   `update_entity_transform`: `0` (The entity's transform is not directly updated by this body)

### `PhysicsImageShapeComponent`

This component defines the visual shape and collision properties of a physics body using an image.

*   **For Body 1 (Cart Body):**
    *   `body_id`: `1`
    *   `centered`: `1` (The image is centered on the body's origin)
    *   `image_file`: `data/props_gfx/cart_top.png` (The sprite for the cart's main body)
    *   `material`: `wood_prop` (Defines physical properties like friction and density)

*   **For Body 2 (Wheel Body):**
    *   `body_id`: `2`
    *   `centered`: `1`
    *   `is_circle`: `1` (Defines a circular shape)
    *   `image_file`: `data/props_gfx/cart_wheel.png` (The sprite for the wheel)
    *   `z`: `1` (Rendering layer)
    *   `material`: `wood_prop`

### `PhysicsJointComponent`

This component connects two physics bodies, simulating a joint.

*   `body1_id`: `1` (Connects to the cart body)
*   `body2_id`: `2` (Connects to the wheel body)
*   `pos_x`: `10.5` (Offset from body1's origin for the joint connection point)
*   `pos_y`: `7.5` (Offset from body1's origin for the joint connection point)

This specific joint configuration likely creates a pivot point, allowing the wheel to rotate relative to the cart body.

### `CameraBoundComponent`

This component controls how the entity interacts with the camera.

*   `max_count`: `50` (Maximum number of this entity type that can be active within the camera's view)
*   `distance`: `500` (The maximum distance from the camera at which this entity will be rendered or processed)