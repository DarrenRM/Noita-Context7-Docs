---
title: True Orbit Projectile Behavior
category: scripts
---

# True Orbit Projectile Behavior

This script defines the behavior for projectiles that orbit their owner. It dynamically adjusts the projectile's position and velocity to create an orbital path.

## Core Functionality

The primary goal of this script is to make a projectile follow a circular or elliptical path around its caster.

### Key Attributes & Elements

*   **`ProjectileComponent`**: This component is essential for identifying the entity as a projectile and accessing its properties like `mWhoShot`.
*   **`VariableStorageComponent`**: Used to store and retrieve custom variables for the projectile:
    *   `true_orbit_dist`: Stores the current orbital distance.
    *   `true_orbit_dir`: Stores a multiplier that influences the direction of the orbit.
*   **`VelocityComponent`**: Manages the projectile's velocity, which is updated to simulate orbital movement.
*   **Owner Tracking**: The script identifies the projectile's owner using `mWhoShot` from the `ProjectileComponent`.
*   **Dynamic Orbit Adjustment**: The script can adjust the orbital distance and direction based on the projectile's current velocity and the owner's facing direction.

## Script Logic Breakdown

1.  **Initialization**:
    *   Retrieves the projectile's entity ID and its current position.
    *   Identifies the owner of the projectile.

2.  **Orbit Calculation**:
    *   If the projectile has an owner and the necessary `VariableStorageComponent`s are present:
        *   It fetches the owner's position.
        *   It retrieves the current orbital distance (`dist`) and direction multiplier (`dirmult`).

3.  **Close Orbit Behavior (Distance < 16)**:
    *   When the projectile gets close to the owner (distance less than 16 units), the script recalculates the `dist` based on the projectile's current velocity. This helps to prevent the projectile from getting stuck or behaving erratically at very close ranges.
    *   The `dirmult` is set to the owner's horizontal facing direction (`psx`).
    *   The `ProjectileComponent`'s `collide_with_world` and `die_on_low_velocity` are set to `0` to allow continuous orbiting without immediate collision or death.

4.  **Position and Velocity Update**:
    *   Calculates the target position for the projectile based on the owner's position, the orbital distance, and an adjusted direction. The `dirmult` influences this adjustment.
    *   Updates the projectile's transform to the new calculated position.
    *   Calculates the difference in position (delta) from the previous frame.
    *   Updates the `VelocityComponent` with this delta, effectively setting the projectile's velocity to match its movement.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity that is spawned by a spell or weapon. The spell/weapon would be responsible for:

1.  Creating the projectile entity.
2.  Adding a `ProjectileComponent` to it.
3.  Adding `VariableStorageComponent`s named `true_orbit_dist` and `true_orbit_dir` with initial values.
4.  Adding a `VelocityComponent`.
5.  Attaching this `true_orbit.lua` script to the projectile.

The initial values for `true_orbit_dist` and `true_orbit_dir` would determine the starting orbit. For instance, a larger `true_orbit_dist` would create a wider orbit.