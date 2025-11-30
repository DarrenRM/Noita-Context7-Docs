---
title: Gravity Field Script
category: scripts
---

# Gravity Field Script

This script implements a gravity field effect that attracts projectiles within its radius.

## Core Functionality

The script iterates through all entities tagged as "projectile" and applies a gravitational pull towards the entity running this script. The strength of the pull is inversely proportional to the distance from the gravity field.

## Key Attributes and Elements

*   **`entity_id`**: The unique identifier for the entity running this script.
*   **`x`, `y`**: The world coordinates of the gravity field entity.
*   **`projectiles`**: A table containing the IDs of all entities tagged as "projectile".
*   **`distance_full`**: Defines the maximum radius of the gravity field (set to 96 units).
*   **`gravity_coeff`**: A multiplier that scales the gravitational force (set to 96).
*   **`gravity_percent`**: Calculates the percentage of the gravity field's influence based on the projectile's distance.
*   **`direction`**: The angle (in radians) from the projectile to the gravity field.
*   **`VelocityComponent`**: The component on projectile entities that controls their movement. The script directly modifies the `mVelocity` of this component.

## Logic Breakdown

1.  **Get Gravity Field Position**: Retrieves the `entity_id` and its `x`, `y` coordinates.
2.  **Find Projectiles**: Identifies all entities with the "projectile" tag.
3.  **Iterate Through Projectiles**: Loops through each projectile found.
4.  **Calculate Distance**:
    *   Calculates the Manhattan distance (`math.abs( x - px ) + math.abs( y - py )`) for an initial broad check.
    *   If the projectile is within a slightly larger radius (`distance_full * 1.25`), it calculates the Euclidean distance (`math.sqrt(...)`) for a more precise check.
5.  **Apply Gravity**:
    *   If the projectile is within the `distance_full` radius:
        *   Calculates `gravity_percent` to determine the influence strength.
        *   Retrieves the `VelocityComponent` of the projectile.
        *   If the `VelocityComponent` exists:
            *   Calculates the `offset_x` and `offset_y` based on the `direction` and the calculated gravitational force (`gravity_coeff * gravity_percent`).
            *   Adds these offsets to the projectile's current velocity (`vel_x`, `vel_y`).
            *   Updates the projectile's `mVelocity` with the new values.

## Example Usage (Conceptual)

This script would typically be attached to an entity that acts as a gravity source, such as a special spell effect or a unique environmental object.

```lua
-- Example of how this script might be triggered by an entity
-- (This is not part of the provided script, but illustrates its context)

-- Assume 'gravity_source_entity' is an entity with this script attached
-- When 'gravity_source_entity' is spawned, the script runs automatically.
```