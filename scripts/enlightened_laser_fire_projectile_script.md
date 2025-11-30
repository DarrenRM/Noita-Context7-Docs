---
title: Enlightened Laser Fire Projectile Script
category: scripts
---

# Enlightened Laser Fire Projectile Script

This script defines the behavior for the "enlightened_laser_fire" projectile in Noita. It handles the projectile's velocity, spawning, and sound effects.

## Key Attributes

*   **Speed:** The projectile travels at a base speed of `400`.
*   **Direction:** The projectile inherits its velocity from the entity that fired it.
*   **Spawning:** It spawns a single projectile (`count = 1`).
*   **Offset:** The spawned projectile has a slight random offset from the firing point.
*   **Projectile Type:** It spawns `data/entities/projectiles/enlightened_laser_fireball.xml`.
*   **Sound Effect:** Plays a specific launch sound effect: `data/audio/Desktop/projectiles.bank`, `projectiles/enlightened_laser/launch_fire`.

## Script Logic

The script first retrieves the projectile's current position and velocity. It then normalizes the velocity and applies the `speed` multiplier. A loop (though currently set to run only once) is used to spawn the projectile. The `shoot_projectile_from_projectile` function is crucial here, as it instantiates the actual projectile entity. Finally, a sound effect is played to indicate the projectile's launch.

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/gun/gun.lua")

local speed = 400

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y, rot = EntityGetTransform( entity_id )

-- velocity
local vel_x,vel_y = GameGetVelocityCompVelocity(entity_id)
vel_x, vel_y = vec_normalize(vel_x, vel_y)
if vel_x == nil then return end -- Exit if velocity is not found
vel_x = vel_x * speed
vel_y = vel_y * speed

local count = 1

SetRandomSeed( pos_x * vel_x, pos_y * vel_y )

for i=1,count do
	local px = pos_x + vel_x * 0.1
	local py = pos_y + vel_y * 0.1
	-- Spawns the actual projectile entity
	shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/enlightened_laser_fireball.xml", px + Random( -5, 5 ), py + Random( -5, 5 ), vel_x, vel_y )
end

-- sound is played here instead of the projectiles to avoid duplicates
GamePlaySound( "data/audio/Desktop/projectiles.bank", "projectiles/enlightened_laser/launch_fire", pos_x, pos_y )
```