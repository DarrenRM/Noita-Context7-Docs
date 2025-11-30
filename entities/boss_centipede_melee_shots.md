---
title: Boss Centipede Melee Shots
category: entities
---

# Boss Centipede Melee Shots

This script defines the projectile behavior for the Boss Centipede's melee attack. It spawns a series of projectiles in a circular pattern around the entity.

## Projectile Spawning Logic

The script calculates the number of projectiles and their angles based on the current run's orb count.

### Key Attributes:

*   **`branches`**: The number of projectiles to spawn. This increases with the `orbcount` for the current run, starting at 8 and increasing by 2 for every 2 orbs collected.
    *   Formula: `8 + math.floor(orbcount / 2) * 2`
*   **`space`**: The angular separation between each projectile. Calculated by dividing 360 degrees by the number of `branches`.
    *   Formula: `math.floor(360 / branches)`
*   **`speed`**: The velocity magnitude of each spawned projectile. Set to `80`.
*   **`angle`**: The initial angle for each projectile, incremented in the loop.

### Projectile Spawning Loop:

The script iterates `branches` times to spawn each projectile.

*   **`shoot_projectile_from_projectile( entity_id, "data/entities/animals/boss_centipede/orb_circleshot.xml", pos_x, pos_y, vel_x, vel_y )`**: This function is used to spawn a new projectile.
    *   `entity_id`: The ID of the projectile that is firing.
    *   `"data/entities/animals/boss_centipede/orb_circleshot.xml"`: The XML definition of the projectile to be spawned.
    *   `pos_x`, `pos_y`: The position from which the projectile is fired.
    *   `vel_x`, `vel_y`: The calculated velocity components for the spawned projectile.

The `vel_x` and `vel_y` are determined using trigonometry (`math.cos` and `math.sin`) based on the current `angle` and `speed`.