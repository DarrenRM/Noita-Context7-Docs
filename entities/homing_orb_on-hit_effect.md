---
title: Homing Orb On-Hit Effect
category: entities
---

# Homing Orb On-Hit Effect

This script defines the behavior when the Homing Orb entity is hit by something. It applies a reactive force to the orb, pushing it away from the source of the damage.

## Key Attributes

*   **`force_mult`**: A multiplier applied to the incoming damage to determine the base force of the reaction.
*   **`force_max`**: The maximum force that can be applied to the orb, preventing excessively strong knockback.

## `damage_received` Function

This function is triggered when the entity receives damage.

### Parameters

*   `damage`: The amount of damage received.
*   `_`: Unused parameter (originally for message).
*   `hitter`: The entity ID of the object that caused the damage.

### Logic

1.  **Get Entity Information**: Retrieves the `entity_id` and its current `pos_x`, `pos_y` coordinates.
2.  **Calculate Force**:
    *   Calculates the initial `force` by multiplying `damage` with `force_mult`.
    *   Clamps the `force` to a maximum value using `math.min(force, force_max)`.
3.  **Determine Direction**:
    *   Gets the transform (position) of the `hitter`.
    *   Checks if the positions of the orb and the hitter are valid. If not, the function returns.
    *   Calculates the vector from the `hitter` to the orb using `vec_sub`.
    *   Normalizes this vector to get a direction using `vec_normalize`.
    *   Multiplies the normalized direction vector by the calculated `force` to get the final push vector (`x`, `y`).
4.  **Apply Velocity Change**:
    *   Uses `edit_component` to modify the `VelocityComponent` of the orb.
    *   Retrieves the current velocity (`vel_x`, `vel_y`).
    *   Adds the calculated push vector (`x`, `y`) to the current velocity.
    *   Sets the new velocity for the orb.