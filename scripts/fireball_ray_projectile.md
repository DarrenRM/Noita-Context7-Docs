---
title: Fireball Ray Projectile
category: scripts
---

---

# Fireball Ray Projectile

This script defines the behavior for a "fireball ray" projectile in Noita, likely used as a component within a wand or spell. It focuses on spawning a specific projectile entity with a randomized direction and significant velocity.

## Key Attributes

### Projectile Spawning

*   **`shoot_projectile_from_projectile`**: This is the core function used to spawn a new projectile.
    *   **`entity_id`**: The ID of the entity that is currently executing this script (the source of the fireball ray).
    *   **`"data/entities/projectiles/deck/fireball_ray.xml"`**: The XML file defining the properties of the spawned projectile. This is the actual "fireball ray" entity.
    *   **`pos_x`, `pos_y`**: The spawn location of the new projectile, inherited from the source entity.
    *   **`vel_x`, `vel_y`**: The velocity components of the spawned projectile.

### Velocity Calculation

*   **`length = 3000`**: Defines a base magnitude for the projectile's velocity.
*   **`angle = math.rad(Random(0,359))`**: A random angle between 0 and 359 degrees is generated and converted to radians. This determines the direction of the projectile.
*   **`vel_x = math.cos( angle ) * length`**: Calculates the horizontal velocity component based on the random angle and length.
*   **`vel_y = 0 - math.sin( angle ) * length`**: Calculates the vertical velocity component based on the random angle and length. The negation of `math.sin` is used, which is a common convention for y-axis direction in 2D game development.

### Initialization

*   **`SetRandomSeed( GameGetFrameNum() + GetUpdatedComponentID(), pos_x + pos_y + entity_id )`**: This line ensures that the random number generation for the projectile's angle is unique for each instance, preventing identical projectiles from spawning in the same frame. It uses frame number, component ID, and entity position for seeding.