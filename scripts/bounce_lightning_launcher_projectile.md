---
title: Bounce Lightning Launcher Projectile
category: scripts
---

# Bounce Lightning Launcher Projectile

This script defines the behavior for a projectile that launches another projectile, specifically a "bounce lightning" projectile.

## Core Functionality

This script's primary purpose is to act as a launcher. Upon activation, it calculates a random angle and velocity, then fires a `bounce_lightning.xml` projectile from its current position. After launching, the launcher projectile is immediately destroyed.

## Key Attributes

*   **`shoot_projectile_from_projectile`**: This is the core function used to spawn the new projectile.
    *   **`entity_id`**: The ID of the current launcher projectile.
    *   **`"data/entities/projectiles/deck/bounce_lightning.xml"`**: The XML file defining the projectile to be spawned. This indicates it's a lightning-based projectile with bouncing properties.
    *   **`pos_x + shot_vel_x * 0.05`, `pos_y + shot_vel_y * 0.05`**: The spawn position of the new projectile, offset slightly in the direction of its velocity.
    *   **`shot_vel_x`, `shot_vel_y`**: The calculated velocity components for the spawned projectile.
    *   **`false`**: This likely indicates that the spawned projectile is not a "homing" projectile.

*   **Velocity Calculation**:
    *   A random angle is generated using `ProceduralRandom` based on the projectile's position and the current frame number, ensuring varied launch directions.
    *   The `shot_vel_x` and `shot_vel_y` are then calculated using trigonometry (`math.cos`, `math.sin`) with a fixed magnitude of `1000`.

*   **`EntityKill( entity_id )`**: This function immediately destroys the launcher projectile after it has successfully fired the `bounce_lightning` projectile.

## Example Usage (Conceptual)

This script would typically be attached to an entity that is itself a projectile, designed to create a chain reaction or spread effect. For instance, a spell that fires a projectile which then spawns multiple bouncing lightning bolts.

```lua
-- Example of how this script might be invoked (not part of the script itself)
-- Assume 'launcher_projectile_entity' is an entity ID with this script attached.
-- EntityLoad( "data/entities/projectiles/launcher_projectile.xml", x, y )
-- EntityAddChild( parent_entity_id, launcher_projectile_entity )
```