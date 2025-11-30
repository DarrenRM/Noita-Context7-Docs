---
title: Orbit Shot Projectile Logic
category: scripts
---

---

# Orbit Shot Projectile Logic

This script defines the behavior for a projectile that orbits a specific point. It retrieves orbital parameters from a `VariableStorageComponent` and applies them to the projectile's velocity.

## Key Components and Variables

The script primarily interacts with the projectile's `VelocityComponent` and reads configuration from a `VariableStorageComponent`.

### Variable Storage Parameters

The following parameters are expected to be stored in the `VariableStorageComponent` of the projectile entity:

| Parameter Name  | Type    | Description                                     |
|-----------------|---------|-------------------------------------------------|
| `origin_x`      | `float` | The X-coordinate of the orbit's center.         |
| `origin_y`      | `float` | The Y-coordinate of the orbit's center.         |
| `orbit_speed`   | `int`   | The speed of the orbit in degrees per frame.    |
| `rot_speed`     | `float` | The rotational speed or magnitude of the velocity. |

### Velocity Component Manipulation

The script modifies the `mVelocity` of the `VelocityComponent` to achieve the orbiting effect.

## Core Logic

1.  **Entity Initialization**: Retrieves the current entity ID and its transform (position).
2.  **Parameter Retrieval**:
    *   It searches for a `VariableStorageComponent`.
    *   If found, it iterates through its variables to extract `origin_x`, `origin_y`, `orbit_speed`, and `rot_speed`.
3.  **Velocity Calculation**:
    *   If all necessary parameters are successfully retrieved:
        *   It calculates the direction vector from the projectile's current position to the orbit origin.
        *   The `orbit_speed` is converted to radians.
        *   The projectile's velocity (`vel_x`, `vel_y`) is calculated using trigonometry (cosine and sine) based on the current direction, orbit speed, and rotational speed. This effectively makes the projectile move in a circular path around the origin.
        *   The calculated velocity is applied to the `VelocityComponent`.