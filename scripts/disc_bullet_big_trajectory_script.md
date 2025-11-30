---
title: Disc Bullet Big Trajectory Script
category: scripts
---

# Disc Bullet Big Trajectory Script

This script modifies the velocity of a projectile, specifically a "disc bullet," based on its initial trajectory and stored variables. It aims to adjust the projectile's speed and direction, potentially creating a "big" or altered trajectory.

## Key Functionality

This script primarily interacts with the projectile's `VelocityComponent` and `VariableStorageComponent` to:

1.  **Read Initial Velocity:** It retrieves the current velocity vector (`vel_x`, `vel_y`) of the projectile.
2.  **Read Stored Angle and Speed:** It checks for variables named "angle" and "speed" within the projectile's `VariableStorageComponent`. These variables can pre-define the projectile's intended trajectory.
3.  **Calculate Trajectory:**
    *   If "angle" and "speed" are not pre-defined, it calculates them based on the projectile's current velocity.
    *   If they are pre-defined, it uses those values.
4.  **Modify Speed:** It applies a reduction to the projectile's speed if a valid speed value is found.
5.  **Apply New Velocity:** It calculates a new velocity vector based on the adjusted angle and speed, and then updates the projectile's `VelocityComponent`.

## Core Components and Variables

### `VelocityComponent`

This component governs the projectile's movement. The script reads and writes to its `mVelocity` property.

### `VariableStorageComponent`

This component is used to store custom variables. The script specifically looks for:

*   **`name`**: "angle"
    *   **`value_string`**: Stores the desired angle in degrees.
*   **`name`**: "speed"
    *   **`value_string`**: Stores the desired speed.

## Script Logic Breakdown

1.  **Initialization:**
    *   Retrieves the projectile's entity ID and current position.
    *   Initializes `angle`, `speed`, `vel_x`, and `vel_y` to default values.

2.  **Variable Reading:**
    *   Iterates through `VariableStorageComponent`s attached to the entity.
    *   If a variable named "angle" or "speed" is found, its `value_string` is parsed as a number and stored.

3.  **Velocity Component Access:**
    *   Uses `edit_component` to access and read the current `mVelocity` from the `VelocityComponent`.

4.  **Speed Adjustment:**
    *   If a `speed` was successfully read from variables and is greater than -200, it is reduced by 60. This is a key part of the "big trajectory" effect, likely slowing it down initially.

5.  **Trajectory Calculation and Storage:**
    *   **If `angle` or `speed` were not pre-defined:**
        *   Calculates the `angle` based on the current `vel_y` and `vel_x` using `math.atan2` and converts it to degrees.
        *   Calculates the `speed` using the Pythagorean theorem on `vel_x` and `vel_y`.
        *   Updates the "angle" and "speed" variables in the `VariableStorageComponent` with these newly calculated values.
    *   **If `angle` or `speed` were pre-defined:**
        *   Updates the "speed" variable in the `VariableStorageComponent` with the potentially modified speed.

6.  **New Velocity Application:**
    *   Converts the final `angle` to radians.
    *   Defines a `multiplier` of `0.1`.
    *   Calculates the new `vel_x` and `vel_y` by adding a component of the `speed` in the direction of the `angle`, scaled by the `multiplier`.
    *   Uses `edit_component` to update the `mVelocity` in the `VelocityComponent` with the newly calculated `vel_x` and `vel_y`.

## Example Usage (Conceptual)

To make a projectile follow a specific trajectory with this script, you would typically:

1.  Create a projectile entity.
2.  Add a `VelocityComponent` to it.
3.  Add a `VariableStorageComponent`.
4.  Within the `VariableStorageComponent`, add two variables:
    *   `name`: "angle", `value_string`: "45" (for 45 degrees)
    *   `name`: "speed", `value_string`: "500" (for a speed of 500)
5.  Attach this script to the projectile entity.

The script would then read these values, potentially adjust the speed, and apply the resulting velocity.