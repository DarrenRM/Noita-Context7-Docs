---
title: Green Dragon Orb Projectile Spawner
category: scripts
---

# Green Dragon Orb Projectile Spawner

This script controls the behavior of a projectile spawner, specifically for the "Green Dragon Orb" in Noita. When triggered, it spawns multiple smaller projectiles in a circular pattern around the spawner's location.

## Key Functionality

*   **Delayed Spawning:** The script includes a `script_wait_frames( entity_id, 10 )` check to ensure projectiles are not spawned too rapidly, with a 10-frame delay between spawns.
*   **Circular Projectile Pattern:** It calculates and spawns `how_many` (defaulting to 10) projectiles. Each projectile is given a velocity vector that positions it in a circular arrangement around the spawner.
*   **Projectile Type:** The projectiles spawned are of the type `data/entities/projectiles/orb_green_boss_dragon.xml`.
*   **Sound Effects:** Plays a "duplicate" sound for each spawned projectile and a distinct "projectiles/orb_dragon/create" sound at the spawner's location upon activation.

## Core Attributes

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `how_many`    | The number of smaller projectiles to spawn.                              |
| `angle_inc`   | The angular increment between each spawned projectile.                   |
| `theta`       | The current angle used to calculate projectile velocity.                 |
| `length`      | The magnitude of the velocity vector for the spawned projectiles.        |
| `px`, `py`    | The calculated spawn position for each projectile, offset from the spawner. |
| `vel_x`, `vel_y` | The calculated velocity vector for each spawned projectile.              |

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- check that we're only shooting every 10 frames
if script_wait_frames( entity_id, 10 ) then  return  end

local how_many = 10
local angle_inc = ( 2 * 3.14159 ) / how_many
local theta = 0
local length = 100

for i=1,how_many do
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc
	
	local px = pos_x + vel_x * 0.1
	local py = pos_y + vel_y * 0.1

	GameEntityPlaySound( entity_id, "duplicate" )
	shoot_projectile( entity_id, "data/entities/projectiles/orb_green_boss_dragon.xml", px, py, vel_x, vel_y )
end

GamePlaySound( "data/audio/Desktop/projectiles.bank", "projectiles/orb_dragon/create", pos_x, pos_y )
```