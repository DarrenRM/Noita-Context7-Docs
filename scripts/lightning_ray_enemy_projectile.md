---
title: Lightning Ray Enemy Projectile
category: scripts
---

---

# Lightning Ray Enemy Projectile

This script defines the behavior for a lightning ray projectile fired by enemies in Noita. It's designed to create a powerful, long-range electrical discharge.

## Key Attributes

*   **Projectile Type:** `lightning_extra_arcs.xml` - This indicates the visual and functional definition of the projectile, likely involving multiple electrical arcs.
*   **Origin:** The projectile originates from the entity that executes this script.
*   **Position:** The projectile is spawned at the current `pos_x` and `pos_y` of the originating entity.
*   **Velocity:** The projectile is launched with a velocity determined by a random angle and a fixed `length` of 3000 units. This creates a sweeping or directed electrical blast.

## Script Logic

1.  **Initialization:**
    *   Retrieves the `entity_id` of the current entity and its root.
    *   Gets the `pos_x` and `pos_y` of the entity.
    *   Sets a random seed based on game frame, component ID, and entity position for varied behavior.

2.  **Angle and Length Determination:**
    *   A random `angle` between 0 and 359 degrees is generated.
    *   A fixed `length` of 3000 units is set for the projectile's travel distance or effect.

3.  **Velocity Calculation:**
    *   `vel_x` and `vel_y` are calculated using trigonometry (`math.cos` and `math.sin`) based on the random `angle` and `length`.

4.  **Projectile Spawning:**
    *   The `shoot_projectile` function is called to create the actual projectile.
    *   It uses the originating `entity_id`, the projectile definition `data/entities/projectiles/deck/lightning_extra_arcs.xml`, the spawn position (`pos_x`, `pos_y`), and the calculated velocity (`vel_x`, `vel_y`).