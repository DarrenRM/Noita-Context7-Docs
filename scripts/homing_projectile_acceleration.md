---
title: Homing Projectile Acceleration
category: scripts
---

# Homing Projectile Acceleration

This script modifies the `HomingComponent` of a projectile, causing it to gradually increase its homing ability and velocity over time.

## Key Components Modified

### `HomingComponent`

This component is responsible for the projectile's ability to track and move towards a target.

#### Key Attributes:

*   **`homing_targeting_coeff`**: Controls how strongly the projectile aims towards its target. This script increases this value over time, making the projectile more accurate.
*   **`homing_velocity_multiplier`**: Affects the projectile's speed when actively homing. This script increases this multiplier, making the projectile faster as it homes.

## Script Logic

The script performs the following actions:

1.  **Get Entity ID**: Retrieves the unique identifier for the projectile entity.
2.  **Check for `HomingComponent`**: Verifies if the projectile has a `HomingComponent` attached. If not, the script exits.
3.  **Edit Component**: If the `HomingComponent` exists, the script accesses its properties.
4.  **Increase Targeting and Velocity**:
    *   `homing_targeting_coeff` is incremented by 2, capped at a maximum of 800.
    *   `homing_velocity_multiplier` is incremented by 0.01, capped at a maximum of 2.0.

This results in projectiles that start with a certain homing capability and speed, and become progressively more aggressive in their pursuit of a target.