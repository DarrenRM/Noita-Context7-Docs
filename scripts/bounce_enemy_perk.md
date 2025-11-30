---
title: Bounce Enemy Perk
category: scripts
---

---

# Bounce Enemy Perk

This script modifies projectile behavior to make enemies bounce projectiles back at the player.

## Key Functionality

The `shot` function is triggered when a projectile is fired. It iterates through the projectile's components and applies the following modifications:

### Projectile Component Modifications

*   **`bounce_always`**: Set to `true`, ensuring the projectile will always bounce.
*   **`bounce_at_any_angle`**: Set to `true`, allowing bounces regardless of the impact angle.
*   **`bounce_energy`**: Set to `0.9`, meaning the projectile retains 90% of its energy after each bounce.
*   **`bounces_left`**: Increased by 10, granting more bounces.
*   **`lifetime`**: If the projectile has a defined lifetime, it is increased by 60 seconds.