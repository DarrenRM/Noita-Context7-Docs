---
title: Boss Meat Acid Shot Projectile
category: entities
---

# Boss Meat Acid Shot Projectile

This script defines the behavior for a projectile fired by the "Boss Meat" entity. It calculates a random angle and velocity to launch an `acidshot_slow.xml` projectile.

## Key Attributes

*   **Projectile Type:** `data/entities/animals/boss_meat/acidshot_slow.xml` - This specifies the visual and behavioral characteristics of the projectile itself.
*   **Launch Origin:** The projectile is fired from the current position (`x`, `y`) of the entity executing this script.
*   **Velocity Calculation:**
    *   A random angle is generated between 0 and 360 degrees.
    *   This angle is used to calculate horizontal (`vx`) and vertical (`vy`) velocity components, resulting in a projectile speed of 90 units.

## Script Logic

1.  **Initialization:**
    *   Includes the `utilities.lua` script for helper functions.
    *   Retrieves the unique ID of the current entity.
    *   Gets the current `x` and `y` coordinates of the entity.

2.  **Randomization:**
    *   Sets a random seed based on the entity's position and the current game frame to ensure varied projectile trajectories.
    *   Generates a random floating-point number between 0 and 1 (`rnd`).

3.  **Angle and Velocity Calculation:**
    *   Calculates a random `angle` in radians, covering a full circle (0 to 2π).
    *   Determines the `vx` (horizontal velocity) using `math.cos(angle) * 90`.
    *   Determines the `vy` (vertical velocity) using `-math.sin(angle) * 90`. The negative sign ensures projectiles are generally fired upwards and outwards, depending on the angle.

4.  **Projectile Firing:**
    *   Calls the `shoot_projectile` function to create and launch the projectile.
        *   `entity_id`: The entity that is firing.
        *   `"data/entities/animals/boss_meat/acidshot_slow.xml"`: The XML file defining the projectile.
        *   `x`, `y`: The origin coordinates for the shot.
        *   `vx`, `vy`: The calculated velocity components.