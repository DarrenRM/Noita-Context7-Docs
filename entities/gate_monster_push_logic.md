---
title: Gate Monster Push Logic
category: entities
---

# Gate Monster Push Logic

This script defines the behavior for a "gate monster" entity in Noita, specifically its ability to push away other nearby gate monsters.

## Core Functionality

The primary purpose of this script is to prevent multiple "gate monster" entities from clustering together. When a gate monster spawns or is active, it checks for other entities tagged with "gate_monster" within a certain radius. If found, it applies a repulsive force to push them away.

## Key Attributes & Elements

*   **`entity_id`**: A unique identifier for the current gate monster entity.
*   **`pos_x`, `pos_y`**: The current world coordinates of the gate monster.
*   **`EntityGetInRadiusWithTag(pos_x, pos_y, 90, "gate_monster")`**: This function searches for entities tagged with "gate_monster" within a 90-unit radius around the current gate monster.
*   **`id ~= entity_id`**: Ensures that the gate monster does not apply force to itself.
*   **`EntityGetTransform(id)`**: Retrieves the position of a found "gate_monster" entity.
*   **`vec_normalize(x, y)`**: Normalizes a vector, returning a unit vector in the same direction.
*   **`vec_mult(x, y, 800)`**: Multiplies a vector by a scalar value (800 in this case), determining the strength of the repulsive force.
*   **`PhysicsApplyForce(id, x, y)`**: Applies a calculated force to the target "gate_monster" entity, pushing it away.

## Logic Flow

1.  Get the unique ID and current position of the gate monster.
2.  Iterate through all entities within a 90-unit radius that are tagged as "gate_monster".
3.  For each found "gate_monster" (excluding itself):
    *   Calculate the vector pointing from the current gate monster to the other.
    *   Normalize this vector to get a direction.
    *   Scale the normalized vector by 800 to determine the force magnitude.
    *   Apply this calculated force to the other "gate_monster" entity, pushing it away.