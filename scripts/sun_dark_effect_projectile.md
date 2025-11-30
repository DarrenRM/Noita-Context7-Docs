---
title: Sun Dark Effect Projectile
category: scripts
---

---

# Sun Dark Effect Projectile

This script defines the behavior for a projectile spawned by the "Sun Dark Effect" building in Noita. When triggered, it shoots a lightning projectile in a random direction.

## Key Attributes

### Projectile Spawning

*   **`entity_id`**: The ID of the entity that triggered this script.
*   **`x`, `y`**: The world coordinates where the projectile will be spawned.
*   **`angle`**: A randomly generated angle (0-359 degrees) determining the projectile's direction.
*   **`length`**: The magnitude of the projectile's velocity.
*   **`vel_x`, `vel_y`**: Calculated velocity components based on the `angle` and `length`.
*   **`shoot_projectile`**: The function used to create and launch the projectile.

### Projectile Type

*   **`"data/entities/projectiles/lightning.xml"`**: Specifies that the spawned projectile is of the "lightning" type.

## Script Logic

1.  **Initialization**: Retrieves the `entity_id` and its world coordinates (`x`, `y`).
2.  **Random Seed**: Sets a random seed based on game frame and entity information to ensure varied projectile behavior.
3.  **Direction Calculation**:
    *   Generates a random `angle` in degrees.
    *   Converts the angle to radians for trigonometric calculations.
    *   Calculates the `vel_x` and `vel_y` components of the projectile's velocity.
4.  **Projectile Launch**: Calls `shoot_projectile` to create and fire the lightning projectile from the current entity's position with the calculated velocity.