---
title: Small Lightning Explosion Projectile
category: scripts
---

# Small Lightning Explosion Projectile

This script defines the behavior for a small lightning explosion projectile in Noita. When spawned, it creates multiple instances of a "lightning" projectile, radiating outwards from the explosion's origin.

## Key Attributes

*   **Projectile Creation:** The script is responsible for spawning multiple instances of `data/entities/projectiles/deck/lightning.xml`.
*   **Number of Projectiles:** `how_many` controls the quantity of lightning projectiles spawned.
*   **Angular Distribution:** `angle_inc` determines the spacing between the spawned projectiles, with a procedural random element for variation.
*   **Velocity Magnitude:** `length` sets the speed/magnitude of the velocity for each spawned projectile.

## Script Logic

The script first retrieves the current entity's ID and its position. It then calculates an initial angle increment (`angle_inc`) for distributing the projectiles. A loop iterates `how_many` times, calculating the velocity vector for each projectile based on the current angle (`theta`) and the defined `length`. Finally, `shoot_projectile` is called to spawn each lightning projectile.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local how_many = 4 -- Number of lightning projectiles to spawn
-- Calculate the angle increment with procedural randomness
angle_inc = ( 2 * 3.14159 ) / how_many + math.rad(ProceduralRandomf( pos_x, pos_y, 30) - ProceduralRandomf( pos_x + 2.5532, pos_y + 59.8, 30))
local theta = 0 -- Initial angle
local length = 2500 -- Velocity magnitude for spawned projectiles

for i=1,how_many do
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc

	-- Shoot a lightning projectile
	shoot_projectile( entity_id, "data/entities/projectiles/deck/lightning.xml", pos_x, pos_y, vel_x, vel_y )
end
```