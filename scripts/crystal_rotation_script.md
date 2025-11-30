---
title: Crystal Rotation Script
category: scripts
---

# Crystal Rotation Script

This script applies a torque and a downward force to an entity, causing it to rotate and fall. It's likely intended for decorative or environmental elements that should exhibit dynamic behavior.

## Key Attributes

*   **`entity_id`**: The unique identifier for the entity this script is attached to.
*   **`x`, `y`, `rot`**: The current position (x, y) and rotation of the entity.

## Core Logic

The script performs the following actions:

### Physics Application

*   **`PhysicsApplyTorque(entity_id, -rot * 20)`**: Applies a rotational force (torque) to the entity. The magnitude of the torque is dependent on the entity's current rotation (`rot`), multiplied by a factor of 20. The negative sign suggests a torque that attempts to counteract or influence the current rotation in a specific direction.
*   **`PhysicsApplyForce(entity_id, 0, -30)`**: Applies a constant downward force to the entity. The force is applied along the Y-axis (0 in the X direction, -30 in the Y direction), simulating gravity or a push downwards.

## Usage Notes

This script is designed to be attached to an entity within the Noita game engine. It requires the entity to have physics properties enabled for the `PhysicsApplyTorque` and `PhysicsApplyForce` functions to have an effect. The specific visual outcome will depend on the entity's sprite and collision shape.