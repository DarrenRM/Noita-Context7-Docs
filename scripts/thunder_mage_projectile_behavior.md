---
title: Thunder Mage Projectile Behavior
category: scripts
---

# Thunder Mage Projectile Behavior

This script defines the behavior for a projectile fired by the Thunder Mage entity in Noita. It focuses on generating a single, powerful electrical projectile with a random initial direction.

## Key Attributes

### Projectile Generation

*   **`shoot_projectile`**: This is the core function responsible for creating and launching the projectile.
    *   **`entity_id`**: The ID of the entity firing the projectile (the Thunder Mage).
    *   **`"data/entities/misc/electricity.xml"`**: Specifies the XML file defining the projectile's appearance and properties.
    *   **`pos_x`, `pos_y`**: The starting coordinates of the projectile, taken from the Thunder Mage's current position.
    *   **`vel_x`, `vel_y`**: The initial velocity components of the projectile.

### Velocity Calculation

The script calculates the projectile's initial velocity to ensure it travels in a random direction with a consistent magnitude.

*   **`theta`**: A random angle in radians, generated between 1 and 360 degrees. This determines the projectile's direction.
*   **`length`**: A fixed value (5000) representing the magnitude of the projectile's velocity.
*   **`vel_x = math.cos( theta ) * length`**: Calculates the horizontal component of the velocity.
*   **`vel_y = 0 - math.sin( theta ) * length`**: Calculates the vertical component of the velocity. The negation of `math.sin` is used to align with Noita's coordinate system where positive Y is typically downwards.

### Initialization

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Ensures that utility functions are loaded and available.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity executing this script.
*   **`EntityGetTransform( entity_id )`**: Gets the current position (x, y) of the entity.
*   **`SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )`**: Initializes the random number generator using the current frame number and the entity's position and ID. This helps ensure that each projectile fired has a unique, yet deterministic, random trajectory for a given game state.