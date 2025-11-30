---
title: Enlightened Laser Light Projectile
category: scripts/
---

# Enlightened Laser Light Projectile

This script defines the behavior of the "Enlightened Laser Light" projectile in Noita. It's a projectile that spawns multiple smaller light beams in its wake and plays a distinct sound effect upon launch.

## Key Attributes

*   **Speed:** The base speed of the projectile.
*   **Count:** The number of secondary light beams spawned.
*   **Spawn Offset:** Random variation applied to the spawn position of secondary beams.
*   **Projectile Type:** The XML file defining the appearance and behavior of the spawned secondary projectiles.
*   **Sound Effect:** The audio bank and event played when the projectile is launched.

## Script Logic

The script performs the following actions:

1.  **Initialization:**
    *   Includes necessary utility and gun scripts.
    *   Sets the projectile's `speed` to 400.
    *   Retrieves the current entity ID and its transform (position and rotation).
    *   Gets the current velocity of the projectile.

2.  **Velocity Calculation:**
    *   Normalizes the velocity vector to ensure consistent direction.
    *   Applies the `speed` to the normalized velocity to determine the final `vel_x` and `vel_y`.

3.  **Secondary Projectile Spawning:**
    *   Sets a `count` of 5 for the number of secondary projectiles to spawn.
    *   Uses `SetRandomSeed` for varied projectile placement.
    *   Iterates `count` times:
        *   Calculates a spawn position slightly ahead of the main projectile's current position.
        *   Uses `shoot_projectile_from_projectile` to spawn `enlightened_laser_lightbeam.xml` projectiles.
        *   Applies a random offset (`Random(-5, 5)`) to the spawn position for each secondary projectile.

4.  **Sound Playback:**
    *   Plays the "launch\_light" sound effect from the "projectiles/enlightened\_laser" bank. This is done on the main projectile to prevent duplicate sounds from the spawned beams.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/gun/gun.lua")
local speed = 400

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y, rot = EntityGetTransform( entity_id )

-- velocity
local vel_x,vel_y = GameGetVelocityCompVelocity(entity_id)
vel_x, vel_y = vec_normalize(vel_x, vel_y)
if vel_x == nil then return end
vel_x = vel_x * speed
vel_y = vel_y * speed

local count = 5

SetRandomSeed( pos_x * vel_x, pos_y * vel_y )

for i=1,count do
	local px = pos_x + vel_x * 0.1
	local py = pos_y + vel_y * 0.1
	shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/enlightened_laser_lightbeam.xml", px + Random( -5, 5 ), py + Random( -5, 5 ), vel_x, vel_y )
end

-- sound is played here instead of the projectiles to avoid duplicates
GamePlaySound( "data/audio/Desktop/projectiles.bank", "projectiles/enlightened_laser/launch_light", pos_x, pos_y )
```