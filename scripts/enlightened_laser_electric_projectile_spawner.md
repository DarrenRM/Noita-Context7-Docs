---
title: Enlightened Laser Electric Projectile Spawner
category: scripts
---

# Enlightened Laser Electric Projectile Spawner

This script defines the behavior for spawning multiple "enlightened laser electric beam" projectiles. It's designed to be attached to a projectile entity that acts as a spawner.

## Key Attributes

*   **`speed`**: The base speed at which the spawned projectiles will travel.
    *   Value: `4000`
*   **`count`**: The number of projectiles to spawn.
    *   Value: `3`

## Spawning Logic

The script calculates the initial velocity based on the spawner entity's transform and then spawns a specified number of projectiles.

### Projectile Spawning Loop

The core of the script iterates `count` times to create each projectile.

*   **Position Calculation**: Each projectile is spawned slightly offset from the spawner's position, with a small random variation applied to both X and Y coordinates.
    *   `px = pos_x + vel_x * 0.01`
    *   `py = pos_y + vel_y * 0.01`
    *   Random offset: `Random( -8, 8 )` for both X and Y.
*   **Projectile Type**: The projectiles spawned are of the type defined in `data/entities/projectiles/enlightened_laser_elecbeam.xml`.
*   **Velocity**: The spawned projectiles inherit the calculated `vel_x` and `vel_y` from the spawner.

### Sound Handling

The script includes a commented-out line for playing a sound. This indicates that the sound effect for this projectile type is likely handled elsewhere (e.g., in the `enlightened_laser_elecbeam.xml` entity itself or a separate sound manager) to prevent duplicate sounds from being played for each spawned projectile.

```lua
--[[
-- Sound is played here instead of the projectiles to avoid duplicates
--GamePlaySound( "data/audio/Desktop/projectiles.bank", "projectiles/laser/create", pos_x, pos_y )
--]]
```