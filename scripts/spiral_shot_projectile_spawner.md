---
title: Spiral Shot Projectile Spawner
category: scripts
---

# Spiral Shot Projectile Spawner

This script is responsible for spawning multiple "spiral part" projectiles in a circular pattern around the originating projectile.

## Key Functionality

*   **Spawns Projectiles:** Creates several instances of `data/entities/projectiles/deck/spiral_part.xml`.
*   **Circular Formation:** Arranges the spawned projectiles in a spiral or circular pattern.
*   **Variable Storage:** Passes an initial angle (`theta`) to each spawned projectile for its own behavior.

## Core Attributes

*   `how_many`: Determines the number of projectiles to spawn.
*   `angle_inc`: Calculates the angular separation between spawned projectiles.
*   `theta`: The initial angle used to position the first projectile, influenced by game frame for a dynamic spiral.
*   `length`: The distance from the originating projectile at which the new projectiles are spawned.

## Script Logic

The script iterates a set number of times (`how_many`). In each iteration:

1.  It calculates the `x` and `y` coordinates for the new projectile based on the current `theta` and `length`.
2.  It calls `shoot_projectile_from_projectile` to create a new projectile entity.
3.  It retrieves the `VariableStorageComponent` named "theta" from the newly created projectile.
4.  If the component exists, it sets its `value_float` to the current `theta`.
5.  It adds the new projectile as a child of the originating projectile.
6.  It increments `theta` by `angle_inc` for the next projectile.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local how_many = 4 -- Number of projectiles to spawn
local angle_inc = ( 2 * 3.14159 ) / how_many -- Angular increment for circular placement
local theta = math.rad(6)-GameGetFrameNum() / 10.0 -- Initial angle, dynamic with frame number
local length = 16 -- Distance from origin for spawned projectiles

for i=1,how_many do
	local new_x = pos_x + math.cos( theta ) * length
	local new_y = pos_y + math.sin( theta ) * length

	-- Spawn the spiral part projectile
	local eid = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/spiral_part.xml", new_x, new_y, 0, 0 )
	
	-- Set the initial angle for the spawned projectile
	local comp = EntityGetFirstComponent( eid, "VariableStorageComponent", "theta" )
	if ( comp ~= nil ) then
		ComponentSetValue2( comp, "value_float", theta )
	end
	
	EntityAddChild( entity_id, eid )
	
	theta = theta + angle_inc -- Update angle for the next projectile
end
```