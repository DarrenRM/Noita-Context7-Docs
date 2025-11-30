---
title: Bounce Laser Launcher Projectile
category: scripts
---

# Bounce Laser Launcher Projectile

This script defines the behavior for a projectile that, upon reaching a certain velocity threshold, launches multiple `bounce_laser.xml` projectiles in a radial pattern and then destroys itself.

## Core Functionality

The primary purpose of this script is to act as a "burst" projectile. When its own velocity drops below a specific point, it triggers a secondary projectile launch.

## Key Attributes & Logic

### Velocity Threshold

*   **Condition:** `if ( speed < 50 ) then ... end`
    *   This `if` statement checks the current speed of the projectile. If the speed is less than 50 units per second, the projectile will trigger its launch sequence.

### Projectile Spawning

*   **Number of Projectiles:** `local how_many = 4`
    *   Determines how many secondary projectiles are fired.
*   **Initial Angle:** `local angle = math.pi * 0.5`
    *   Sets the starting angle for the first projectile. `math.pi * 0.5` corresponds to straight up (90 degrees).
*   **Angle Increment:** `local angle_inc = (math.pi * 2) / how_many`
    *   Calculates the angular separation between each spawned projectile, ensuring they are evenly distributed in a full circle.
*   **Velocity Calculation:**
    *   `local shot_vel_x = math.cos(angle) * 150`
    *   `local shot_vel_y = 0 - math.sin(angle) * 150`
    *   These lines calculate the X and Y components of the velocity for each spawned projectile using trigonometry. The `150` value represents the base speed of the spawned projectiles.
*   **Spawn Function:** `shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/bounce_laser.xml", pos_x + shot_vel_x * 0.05, pos_y + shot_vel_y * 0.05, shot_vel_x, shot_vel_y, false )`
    *   This function is called within the loop to create and launch the new projectiles.
        *   `entity_id`: The ID of the current projectile.
        *   `"data/entities/projectiles/deck/bounce_laser.xml"`: The XML file defining the projectile to be spawned.
        *   `pos_x + shot_vel_x * 0.05, pos_y + shot_vel_y * 0.05`: The spawn position, slightly offset from the current projectile's position.
        *   `shot_vel_x, shot_vel_y`: The calculated velocity for the spawned projectile.
        *   `false`: Likely indicates whether the spawned projectile should inherit the parent's velocity or direction (in this case, `false` suggests it uses its own calculated velocity).

### Self-Destruction

*   **Kill Entity:** `EntityKill( entity_id )`
    *   After successfully launching the secondary projectiles, the original projectile is destroyed.

## Example Usage (Conceptual)

This script would be attached to a projectile entity that is designed to slow down over time or upon impact. For instance, a projectile that loses momentum after hitting a surface. When its speed drops below 50, it would then release a cluster of `bounce_laser.xml` projectiles.