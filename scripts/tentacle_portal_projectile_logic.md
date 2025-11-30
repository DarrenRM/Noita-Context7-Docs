---
title: Tentacle Portal Projectile Logic
category: scripts
---

# Tentacle Portal Projectile Logic

This script defines the behavior for a projectile that spawns tentacle entities. It includes logic for random direction, homing behavior towards nearby targets, and the projectile's velocity and spawn.

## Key Attributes and Behavior

### Projectile Spawning

-   **`entity_id`**: The unique identifier for the entity executing this script.
-   **`x`, `y`**: The current position of the entity.
-   **`SetRandomSeed`**: Initializes the random number generator based on game frame and entity position for consistent randomness.

### Tentacle Spawning Conditions

-   **`if ( Random( 1, 4 ) > 1 )`**: There's a 75% chance that a tentacle projectile will be spawned.

### Tentacle Projectile Properties

-   **`angle`**: The initial direction of the tentacle projectile.
    -   Defaults to a random angle between 1 and 360 degrees.
    -   Can be adjusted by homing logic.
-   **`length`**: The magnitude of the velocity for the tentacle projectile, ranging from 400 to 700.
-   **`vel_x`, `vel_y`**: Calculated velocity components based on the `angle` and `length`.

### Homing Behavior

-   **`if ( Random( 1, 4 ) > 1 )`**: There's a 75% chance the tentacle projectile will attempt to home in on a target.
-   **`targets = EntityGetWithTag( "homing_target" )`**: Retrieves all entities with the "homing_target" tag.
-   **Target Validation**:
    -   Iterates through found targets.
    -   Calculates Manhattan distance (`math.abs( ty - y ) + math.abs( tx - x )`) to the entity.
    -   Only considers targets within a distance of 72 units.
-   **Target Selection**:
    -   If valid targets are found, one is randomly selected.
    -   The `angle` is then adjusted to point directly at the selected target (`0 - math.atan2( ty - y, tx - x )`).

### Projectile Firing

-   **`shoot_projectile( entity_id, "data/entities/projectiles/deck/tentacle.xml", x, y, vel_x, vel_y )`**: This function is called to spawn the actual tentacle projectile.
    -   **`entity_id`**: The spawner entity.
    -   **`"data/entities/projectiles/deck/tentacle.xml"`**: The XML definition for the tentacle projectile.
    -   **`x`, `y`**: The spawn position.
    -   **`vel_x`, `vel_y`**: The calculated velocity.