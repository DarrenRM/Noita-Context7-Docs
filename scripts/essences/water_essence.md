---
title: Water Essence
category: scripts/essences
---

---

# Water Essence

This script defines the behavior for the Water Essence in Noita. When an entity with this script is activated, it attempts to shoot a "water bullet" projectile from its parent entity.

## Key Attributes

*   **Projectile Type:** `data/entities/misc/essences/water_bullet.xml` - This specifies the XML file that defines the appearance and behavior of the projectile.
*   **Direction:** The projectile is shot in a random direction within a 360-degree arc.
*   **Velocity:** The projectile has a fixed velocity magnitude of `300` units, with its direction determined by the random angle.
*   **Parent Entity:** The script checks if the current entity has a parent. If it does, the projectile is fired from the parent's position.

## Behavior Breakdown

1.  **Initialization:**
    *   Retrieves the `entity_id` and its `pos_x`, `pos_y` coordinates.
    *   Sets a random seed based on the entity's position to ensure varied outcomes.

2.  **Angle Calculation:**
    *   Generates a random angle `theta` between 1 and 360 degrees, converted to radians.

3.  **Velocity Calculation:**
    *   Calculates the `vel_x` and `vel_y` components of the projectile's velocity using trigonometry based on the random angle and a fixed `length` of 300.

4.  **Projectile Firing:**
    *   Checks if the `entity_id` has a `parent_id` (i.e., it's not a top-level entity).
    *   If a parent exists, it calls `shoot_projectile` to fire the `water_bullet.xml` projectile from the parent's position with the calculated velocity.