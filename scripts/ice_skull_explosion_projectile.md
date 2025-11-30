---
title: Ice Skull Explosion Projectile
category: scripts
---

# Ice Skull Explosion Projectile

This script defines the behavior of the "Ice Skull" projectile's explosion. When the Ice Skull projectile hits something, this script is triggered to create a burst of smaller ice projectiles and play a sound effect.

## Key Attributes

*   **Projectile Creation:** Spawns multiple smaller `ice.xml` projectiles in a circular pattern.
*   **Spawn Count:** `how_many` controls the number of spawned projectiles (default: 12).
*   **Spread Angle:** `angle_inc` determines the angular separation between spawned projectiles.
*   **Velocity Magnitude:** `length` sets the speed of the spawned projectiles.
*   **Cooldown:** `script_wait_frames` prevents rapid re-triggering of the explosion (default: 10 frames).
*   **Sound Effect:** Plays a specific sound upon explosion.

## Script Logic

The script first checks for a cooldown period to avoid excessive spawning. If the cooldown has passed, it calculates the velocity vectors for each smaller projectile based on a circular distribution. Finally, it spawns the projectiles and plays the explosion sound.

### Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- check that we're only shooting every 10 frames
if script_wait_frames( entity_id, 10 ) then  return  end

local how_many = 12
local angle_inc = ( 2 * 3.14159 ) / how_many
local theta = 0
local length = 100

for i=1,how_many do
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc

	shoot_projectile( entity_id, "data/entities/projectiles/ice.xml", pos_x, pos_y, vel_x, vel_y )
end

GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/iceskull_explosion/explode", pos_x, pos_y )
```