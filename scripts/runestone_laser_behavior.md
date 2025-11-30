---
title: Runestone Laser Behavior
category: scripts
---

# Runestone Laser Behavior

This script defines the behavior for a runestone that interacts with projectiles, specifically transforming them into lasers.

## Core Functionality

When a runestone with this script is activated, it scans for nearby projectiles. If a projectile is found that does not already have the "laser" tag, it is modified and then replaced with a new laser projectile.

## Key Attributes and Elements

*   **`entity_id`**: The unique identifier for the runestone entity.
*   **`x`, `y`**: The coordinates of the runestone entity.
*   **`projectiles`**: A table containing the IDs of all entities within a 192-unit radius tagged as "projectile".
*   **`tags`**: The tags associated with a projectile. The script checks if "laser" is *not* present in these tags.
*   **`px`, `py`**: The coordinates of the projectile being processed.
*   **`vel_x`, `vel_y`**: The velocity components of the projectile.
*   **`ProjectileComponent`**: Components related to projectile behavior. The script specifically disables `on_death_explode` and `on_lifetime_out_explode` to prevent the original projectile from exploding.
*   **`VelocityComponent`**: Components related to projectile velocity. The script reads the existing velocity.
*   **`shoot_projectile_from_projectile`**: A function that spawns a new projectile from an existing one, using the specified projectile XML (`data/entities/projectiles/deck/laser.xml`) and inheriting the position and velocity.
*   **`EntityKill`**: Used to destroy the original projectile after it has been replaced by the laser.

## Logic Flow

1.  Get the runestone's entity ID and position.
2.  Find all projectiles within a radius.
3.  Iterate through each found projectile.
4.  Check if the projectile has the "laser" tag.
5.  If it does not have the "laser" tag:
    *   Retrieve its position and velocity.
    *   Modify its `ProjectileComponent` to disable explosions.
    *   Read its `VelocityComponent`.
    *   Spawn a new "laser" projectile at the original projectile's location and with its velocity.
    *   Destroy the original projectile.