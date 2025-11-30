---
title: Commander Bullet Homing Behavior
category: scripts
---

# Commander Bullet Homing Behavior

This script defines the behavior of the "commander bullet" projectile in Noita, specifically its ability to home in on other player projectiles and alter its velocity.

## Key Functionality

### Homing Component Integration

When a "commander bullet" projectile encounters another projectile tagged with `"projectile_player"`, it attempts to attach a `HomingComponent`.

*   **`target_tag`**: `"projectile_commander"` - This indicates the commander bullet itself is the target for homing.
*   **`homing_targeting_coeff`**: `"200"` - Controls the strength of the homing effect. A higher value means more aggressive targeting.
*   **`homing_velocity_multiplier`**: `"1.0"` - Multiplies the projectile's existing velocity when homing.

### Velocity Modification

In addition to homing, the script introduces a random offset to the velocity of the player projectile it interacts with.

*   **Random Offset**: A random value between -150 and 150 is added to both the X and Y components of the projectile's velocity. This can cause erratic movement or slight course corrections.

## Script Logic Breakdown

1.  **Initialization**:
    *   Loads utility functions.
    *   Gets the current entity ID and its transform (position).
    *   Sets a random seed based on game frame and position for deterministic randomness.

2.  **Projectile Detection**:
    *   Searches for entities within a 16-unit radius tagged as `"projectile_player"`.

3.  **Homing and Velocity Adjustment**:
    *   Iterates through detected player projectiles.
    *   **Self-Exclusion**: Ensures the commander bullet doesn't target itself.
    *   **Homing Component**: Adds a `HomingComponent` to the player projectile, targeting the commander bullet.
    *   **Velocity Component Access**: Retrieves the `VelocityComponent` of the player projectile.
    *   **Random Velocity Offset**: If a `VelocityComponent` exists, it applies a random offset to the projectile's velocity vector.