---
title: Projectile Slowing Effect
category: scripts/
---

# Projectile Slowing Effect

This script applies a continuous slowing effect to all projectiles currently in the game.

## Core Functionality

The primary purpose of this script is to reduce the velocity of existing projectiles over time.

### Key Attributes/Elements

*   **`entity_id`**: The ID of the entity running this script.
*   **`projectiles`**: A table containing the IDs of all entities tagged as "projectile".
*   **`VelocityComponent`**: The component responsible for managing projectile velocity.
*   **Velocity Reduction**: Each projectile's velocity is multiplied by `0.98` in both X and Y directions during each update cycle. This creates a gradual deceleration.

### How it Works

1.  The script retrieves the ID of the entity executing it.
2.  It then fetches a list of all entities currently tagged as "projectile".
3.  For each projectile found:
    *   It checks if the projectile has a `VelocityComponent`.
    *   If it does, it accesses the `mVelocity` property of the `VelocityComponent`.
    *   The X and Y components of the velocity are multiplied by `0.98`, effectively reducing their speed.
    *   The modified velocity is then applied back to the `VelocityComponent`.

This process repeats continuously, ensuring that all active projectiles are subject to the slowing effect.