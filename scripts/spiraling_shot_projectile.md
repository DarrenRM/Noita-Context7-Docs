---
title: Spiraling Shot Projectile
category: scripts
---

---

# Spiraling Shot Projectile

This script defines the behavior for a projectile that spirals around its owner.

## Key Components and Behavior

The primary function of this script is to modify the projectile's velocity over time, causing it to deviate from a straight path and instead follow a spiraling trajectory.

### Projectile Logic

*   **Owner Identification:** The script first identifies the entity that shot the projectile using `ProjectileComponent` and `mWhoShot`.
*   **Velocity Modification:** If the projectile has an owner, it accesses the `VelocityComponent` of the projectile.
*   **Owner's Transform:** It retrieves the owner's current transform (position and rotation) using `EntityGetTransform`.
*   **Angle Calculation:** The script calculates the current angle of the projectile's velocity.
*   **Spiraling Effect:** It then recalculates the projectile's velocity components (`vel_x`, `vel_y`) by applying a rotation based on the owner's rotation (`psx`) and the projectile's original speed (`dist`). This creates the spiraling effect.

### Relevant Attributes (Conceptual)

While not explicitly listed as attributes in this script, the behavior implies the existence and manipulation of:

*   **`ProjectileComponent`**: Essential for identifying the projectile and its owner.
*   **`VelocityComponent`**: The core component modified to achieve the spiraling motion.
    *   `mVelocity`: The vector representing the projectile's speed and direction.
*   **Entity Transform**: The position and rotation of both the projectile and its owner are crucial for the calculations.