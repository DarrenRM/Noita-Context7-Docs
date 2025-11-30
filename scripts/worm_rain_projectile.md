---
title: Worm Rain Projectile
category: scripts
---

# Worm Rain Projectile

This script defines the behavior for a projectile that triggers a "worm rain" effect. When this projectile is activated, it spawns a large worm entity at a random position relative to its own location and causes a screen shake.

## Key Attributes

*   **`entity_id`**: The unique identifier for the projectile entity.
*   **`pos_x`, `pos_x`**: The current X and Y coordinates of the projectile.
*   **`x`, `y`**: The calculated spawn coordinates for the worm, offset from the projectile's position.
*   **`eid`**: The entity ID of the spawned worm.

## Functionality

1.  **Initialization**: Retrieves the projectile's entity ID and its current position.
2.  **Randomization**: Sets a random seed based on game frame, component ID, and entity position to ensure varied outcomes.
3.  **Spawn Position Calculation**: Determines a random X coordinate within a range of -200 to 200 and a random Y coordinate within a range of -300 to -160, relative to the projectile's position.
4.  **Worm Spawning**: Loads the `worm_big_worm_rain.xml` entity at the calculated random coordinates.
5.  **Screen Shake**: Triggers a screen shake with an intensity of 10.

## Related Files

*   `data/entities/misc/worm_big_worm_rain.xml`: The entity definition for the large worm that is spawned.