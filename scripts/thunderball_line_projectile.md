---
title: Thunderball Line Projectile
category: scripts
---

---

# Thunderball Line Projectile

This script defines the behavior for a projectile that spawns other projectiles in a line.

## Core Functionality

The `thunderball_line.lua` script is responsible for creating a series of `thunderball_slow.xml` projectiles originating from the current projectile's position.

### Key Attributes

*   **`entity_id`**: The unique identifier for the current projectile entity.
*   **`pos_x`, `pos_y`**: The current world coordinates of the projectile.
*   **`angle`**: A randomly generated angle (0-359 degrees) used to determine the direction of the spawned projectiles.
*   **`length`**: A fixed value (40) that influences the velocity of the spawned projectiles.
*   **`vel_x`, `vel_y`**: Calculated velocity components for the spawned projectiles based on the `angle` and `length`.

## Spawning Mechanism

The script utilizes the `shoot_projectile_from_projectile` function to spawn new projectiles.

### `shoot_projectile_from_projectile` Parameters

*   **`entity_id`**: The ID of the projectile that is spawning others.
*   **`"data/entities/projectiles/thunderball_slow.xml"`**: The XML file defining the projectile to be spawned.
*   **`pos_x`, `pos_y`**: The spawn location for the new projectiles.
*   **`vel_x`, `vel_y`**: The initial velocity applied to the spawned projectiles.

## Randomization

The script incorporates randomization to ensure variability in the spawned projectiles' direction.

### `SetRandomSeed`

This function is used to seed the random number generator, making the projectile behavior less predictable across different game instances. It uses frame number, component ID, and position to create a unique seed.

### `Random(0, 359)`

Generates a random angle between 0 and 359 degrees, determining the spread of the spawned projectiles.