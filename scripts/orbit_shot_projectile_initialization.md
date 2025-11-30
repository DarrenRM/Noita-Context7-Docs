---
title: Orbit Shot Projectile Initialization
category: scripts
---

# Orbit Shot Projectile Initialization

This script initializes the `orbit_shot` projectile, setting up its orbiting behavior. It stores the projectile's origin position, calculates a random orbit speed, and records its initial velocity magnitude.

## Key Components and Variables

### Initialization Logic

The script first checks if the projectile already has the `orbit_shot` tag. If not, it proceeds with the initialization:

1.  **Store Origin:** The initial `x` and `y` coordinates of the projectile are stored in `VariableStorageComponent`s named `origin_x` and `origin_y`.
2.  **Random Orbit Speed:** A random orbit speed is generated, ranging from 30 to 70, with a random sign (positive or negative). This speed is stored in a `VariableStorageComponent` named `orbit_speed`.
3.  **Record Initial Velocity:** The projectile's initial velocity (`vel_x`, `vel_y`) is retrieved. The magnitude of this velocity (`spd`) is calculated and stored in a `VariableStorageComponent` named `rot_speed`. This value is likely used to influence the orbiting speed or pattern.
4.  **Apply Tag:** The `orbit_shot` tag is added to the entity to mark it as initialized.

### Relevant Components

*   **`VariableStorageComponent`**: Used extensively to store custom data related to the projectile's behavior.
    *   `origin_x`: Stores the initial X-coordinate.
    *   `origin_y`: Stores the initial Y-coordinate.
    *   `orbit_speed`: Stores the calculated random orbiting speed.
    *   `rot_speed`: Stores the magnitude of the projectile's initial velocity.
*   **`VelocityComponent`**: Used to read the projectile's initial velocity.

### Key Attributes

| Attribute      | Description                                                                                             |
| :------------- | :------------------------------------------------------------------------------------------------------ |
| `origin_x`     | The X-coordinate where the projectile was spawned.                                                      |
| `origin_y`     | The Y-coordinate where the projectile was spawned.                                                      |
| `orbit_speed`  | A random speed value determining how fast the projectile orbits its origin.                             |
| `rot_speed`    | The magnitude of the projectile's initial velocity, potentially used to influence its orbiting behavior. |

```lua
-- Example of how origin_x and origin_y might be used in a subsequent update script:
-- local origin_x = vars.origin_x
-- local origin_y = vars.origin_y
-- local orbit_speed = vars.orbit_speed
-- local current_angle = math.atan2(y - origin_y, x - origin_x)
-- local new_angle = current_angle + orbit_speed * dt -- dt is delta time
-- x = origin_x + math.cos(new_angle) * distance
-- y = origin_y + math.sin(new_angle) * distance
```