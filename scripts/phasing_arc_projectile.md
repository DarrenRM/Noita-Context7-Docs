---
title: Phasing Arc Projectile
category: scripts
---

# Phasing Arc Projectile

This script defines the behavior for a projectile that phases through obstacles.

## Core Functionality

The primary function of this script is to reposition the projectile a fixed distance away from its current location, in the direction opposite to its velocity. This effectively makes it "phase" through whatever it might have hit.

### Key Attributes

*   **`distance`**: Defines the fixed distance the projectile will move. In this script, it's set to `28`.
*   **Velocity Calculation**: The script retrieves the projectile's current velocity to determine its direction.
*   **Direction Calculation**: Uses `math.atan2` to calculate the projectile's current direction of travel.
*   **Offset Calculation**: Determines the offset (`ox`, `oy`) to move the projectile based on the calculated direction and the `distance`.
*   **Entity Repositioning**: Uses `EntitySetTransform` to move the projectile to its new position.

## Script Logic Breakdown

1.  **Initialization**:
    *   Includes `utilities.lua` for helper functions.
    *   Gets the current entity ID and its transform (position `x`, `y`).
    *   Sets a `distance` variable to `28`.

2.  **Velocity Retrieval**:
    *   Attempts to get the `VelocityComponent` of the projectile.
    *   If no `VelocityComponent` is found, the script exits.
    *   Retrieves the `mVelocity` vector (`vel_x`, `vel_y`) from the component.

3.  **Direction and Offset Calculation**:
    *   Calculates the `dir` (direction) using `math.atan2` based on the velocity.
    *   Calculates the horizontal offset (`ox`) using `math.cos` and the `distance`.
    *   Calculates the vertical offset (`oy`) using `math.sin` and the `distance`. Note the negation for `oy` to move in the opposite direction of the calculated angle.

4.  **Entity Transformation**:
    *   Applies the calculated offset to the projectile's current position (`x + ox`, `y + oy`) using `EntitySetTransform`.