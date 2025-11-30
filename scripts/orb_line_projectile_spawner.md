---
title: Orb Line Projectile Spawner
category: scripts
---

# Orb Line Projectile Spawner

This script is responsible for spawning the "orb_line" projectile, which appears to be a visual effect or a projectile related to orbs in the game. It determines the closest orb in the game world and, with a certain probability, shoots a projectile towards the player's current position.

## Key Functionality

*   **Orb Proximity Check:** The script iterates through a list of known orb locations (`orb_map_get()`) to find the one closest to the player.
*   **Projectile Spawning:** If a closest orb is found and a random chance condition is met, it spawns an `orb_line.xml` projectile.
*   **Directional Velocity:** The projectile is launched with a velocity calculated to move from the orb's position towards the player's current position.
*   **Self-Destruction:** After its logic is executed, the entity running this script is killed.

## Core Attributes & Logic

### Orb Detection

The script uses `orb_map_get()` to retrieve orb data. Each entry in `orbdata` is expected to be a table containing coordinates.

```lua
local orbdata = orb_map_get()
```

The script calculates the world coordinates of each orb based on its grid position:

```lua
local ox = v[1] * 512 + 256
local oy = v[2] * 512 + 256
```

It then calculates the distance to the player's current position (`mx`, `y`) using `get_distance`.

### Projectile Spawning

The `shoot_projectile` function is used to create the `orb_line.xml` entity.

```lua
shoot_projectile( entity_id, "data/entities/misc/orb_line.xml", x, y, vel_x, vel_y )
```

*   `entity_id`: The ID of the entity executing this script.
*   `"data/entities/misc/orb_line.xml"`: The XML file defining the projectile's appearance and behavior.
*   `x, y`: The spawn position of the projectile (same as the script's entity).
*   `vel_x, vel_y`: The calculated velocity components for the projectile.

### Random Chance

A random check determines if a projectile is spawned.

```lua
if ( Random( 1, 25 ) == 4 ) then
    -- Spawn projectile logic
end
```

This means there's a 1 in 25 chance (4%) of spawning a projectile on any given frame where this script is active.

### Entity Management

The script ensures that the entity running this logic is removed after its task is complete.

```lua
EntityKill( entity_id )
```