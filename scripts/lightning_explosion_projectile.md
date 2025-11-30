---
title: Lightning Explosion Projectile
category: scripts
---

---

# Lightning Explosion Projectile

This script defines a projectile that creates a burst of smaller lightning projectiles.

## Core Functionality

The primary purpose of this script is to spawn multiple instances of the `lightning.xml` projectile in a radial pattern around the origin of the explosion.

## Key Attributes

*   **`how_many`**: Determines the number of secondary lightning projectiles to spawn.
*   **`angle_inc`**: Calculates the angular separation between each spawned projectile, incorporating procedural randomness for variation.
*   **`length`**: Defines the initial velocity magnitude for the spawned lightning projectiles.
*   **`shoot_projectile`**: The core function used to instantiate and launch the secondary lightning projectiles.

## Script Logic

1.  **Initialization**:
    *   Retrieves the unique ID and position of the entity executing this script.
    *   Sets the number of secondary projectiles (`how_many`) to 4.
    *   Calculates the initial angular increment (`angle_inc`) with procedural randomness.
    *   Initializes the starting angle (`theta`) to 0.
    *   Sets the velocity magnitude (`length`) for the spawned projectiles.

2.  **Projectile Spawning Loop**:
    *   Iterates `how_many` times to spawn each secondary projectile.
    *   In each iteration:
        *   Calculates the velocity components (`vel_x`, `vel_y`) based on the current angle (`theta`) and `length`.
        *   Updates `theta` for the next projectile.
        *   Calls `shoot_projectile` to create a `lightning.xml` projectile at the current entity's position with the calculated velocity.

## Example Usage

This script is typically attached to an entity that should trigger an explosion of lightning bolts, such as a special spell or a unique enemy attack.

```lua
-- Example of how this script might be triggered (not part of the script itself)
-- local explosion_entity = EntityLoad( "data/entities/projectiles/lightning_explosion.xml", x, y )
```