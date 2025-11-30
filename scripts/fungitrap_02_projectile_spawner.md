---
title: Fungitrap 02 Projectile Spawner
category: scripts
---

---

# Fungitrap 02 Projectile Spawner

This script controls the behavior of the `fungitrap_02` entity, specifically its projectile spawning mechanism.

## Core Functionality

The primary function of this script is to periodically spawn projectiles associated with the `fungitrap_02` entity. It checks the number of nearby `fungitrap_02` entities and, if the count is below a threshold, has a chance to fire a projectile.

## Key Attributes and Logic

*   **Entity Identification:**
    *   `GetUpdatedEntityID()`: Retrieves the unique ID of the current `fungitrap_02` entity.
    *   `EntityGetTransform( entity_id )`: Gets the position (x, y) of the entity.

*   **Randomization:**
    *   `SetRandomSeed( GameGetFrameNum(), entity_id + y )`: Initializes the random number generator based on game frame and entity position for varied behavior.
    *   `Random( 1, 7 )`: Generates a random integer between 1 and 7, influencing the chance of firing.
    *   `Random( 1, 180 )`: Generates a random angle in degrees for projectile trajectory.

*   **Projectile Spawning Condition:**
    *   `EntityGetInRadiusWithTag( x, y, 160, "fungitrap_02" )`: Checks for other `fungitrap_02` entities within a 160-unit radius.
    *   `if ( #entities < 4 ) then`: The projectile is only spawned if there are fewer than 4 other `fungitrap_02` entities nearby. This suggests a mechanism to prevent overwhelming the game with projectiles when multiple traps are active.

*   **Projectile Firing:**
    *   `local angle = math.rad( Random( 1, 180 ) )`: Calculates a random firing angle in radians.
    *   `local speed = 200`: Sets a fixed projectile speed.
    *   `local vel_x = math.cos( 0 - angle ) * speed`: Calculates the horizontal velocity component.
    *   `local vel_y = 0 - math.sin( 0 - angle ) * speed`: Calculates the vertical velocity component.
    *   `if ( rnd == 5 ) then`: A random chance (1 in 7) to actually fire the projectile.
    *   `shoot_projectile( entity_id, "data/entities/buildings/fungitrap_02_projectile.xml", x, y, vel_x, vel_y )`: This function (presumably from `utilities.lua`) spawns the projectile.
        *   `entity_id`: The entity that is firing.
        *   `"data/entities/buildings/fungitrap_02_projectile.xml"`: The XML file defining the projectile's properties.
        *   `x, y`: The spawn position of the projectile.
        *   `vel_x, vel_y`: The initial velocity of the projectile.