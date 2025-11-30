---
title: Thunder Trap Projectile
category: scripts
---

# Thunder Trap Projectile

This script defines the behavior of the "Thunder Trap" projectile in Noita. When triggered, it spawns a lightning projectile.

## Key Functionality

The primary function of this script is to initiate a lightning projectile.

### `shoot_projectile`

This function is called to create the lightning projectile.

*   **`entity_id`**: The ID of the entity that triggered the projectile.
*   **`"data/entities/projectiles/lightning.xml"`**: The XML file defining the lightning projectile's properties.
*   **`x, y`**: The spawn coordinates of the lightning projectile, inherited from the trap's position.
*   **`vel_x * 400`**: The horizontal velocity of the lightning projectile. It's significantly amplified from the trap's velocity.
*   **`0`**: The vertical velocity of the lightning projectile.