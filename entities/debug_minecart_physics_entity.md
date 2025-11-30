---
title: Debug Minecart Physics Entity
category: entities
---

# Debug Minecart Physics Entity

This entity defines a basic minecart with physics properties, primarily for debugging purposes. It utilizes multiple `PhysicsImageShapeComponent`s to represent the cart body and its wheels, connected by `PhysicsJoint2Component`s to simulate a revolute joint.

## Key Components

### `PhysicsBody2Component`

This component defines the core physics properties of the entity.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`       | Whether the physics body can enter a sleeping state to save performance. |
| `linear_damping`    | Resistance to linear motion.                                             |
| `kill_entity_after_initialized` | If set to 1, the entity will be destroyed immediately after its physics are initialized. Useful for one-off physics setups. |

### `PhysicsImageShapeComponent`

Used to define the physical shape and appearance of the entity based on an image. This entity uses three: one for the main cart body and two for the wheels.

| Attribute     | Description