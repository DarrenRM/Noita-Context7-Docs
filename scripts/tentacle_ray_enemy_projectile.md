---
title: Tentacle Ray Enemy Projectile
category: scripts
---

# Tentacle Ray Enemy Projectile

This script defines the behavior for a tentacle projectile fired by an enemy in Noita. It calculates a random angle and velocity to launch a "tentacle.xml" projectile from the enemy's position.

## Key Attributes

*   **Projectile Type:** `data/entities/projectiles/deck/tentacle.xml` - This specifies the visual and physical properties of the projectile.
*   **Launch Origin:** The projectile is fired from the `entity_id` of the enemy that spawns it.
*   **Launch Position:** Determined by `EntityGetTransform( entity_id )`, which gets the `pos_x` and `pos_y` of the enemy.
*   **Launch Velocity:**
    *   Calculated based on a random `angle` between 0 and 359 degrees.
    *   The `length` of the velocity vector is set to `3000`.
    *   `vel_x` and `vel_y` are derived using trigonometry (`math.cos` and `math.sin`).
*   **Randomization:** `SetRandomSeed` is used to ensure varied projectile behavior each time, based on game frame and entity properties.

## Script Logic

1.  **Initialization:**
    *   Includes `utilities.lua` for helper functions.
    *   Gets the `entity_id` of the current entity and its root.
    *   Retrieves the `pos_x` and `pos_y` of the enemy.
2.  **Randomization Setup:**
    *   Sets a random seed using `GameGetFrameNum()`, `GetUpdatedComponentID()`, and entity position/ID for unique outcomes.
3.  **Velocity Calculation:**
    *   Generates a random `angle` in degrees and converts it to radians.
    *   Defines a fixed `length` for the projectile's velocity.
    *   Calculates the `vel_x` and `vel_y` components of the velocity vector.
4.  **Projectile Firing:**
    *   Calls `shoot_projectile` to create and launch the tentacle projectile with the calculated parameters.