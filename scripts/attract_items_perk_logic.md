---
title: Attract Items Perk Logic
category: scripts
---

# Attract Items Perk Logic

This script defines the behavior for the "Attract Items" perk in Noita. When active, it pulls nearby gold nuggets towards the player.

## Core Functionality

The perk operates by:
1.  **Identifying Gold:** It searches for entities tagged as "gold_nugget".
2.  **Calculating Distance:** For each gold nugget, it determines the distance from the player.
3.  **Applying Force:** If a gold nugget is within a defined range, a force is applied to move it towards the player.

## Key Attributes and Variables

*   `distance_full`: The maximum range at which items are attracted. This value is read from `GlobalsGetValue` and defaults to "72".
*   `power`: The strength of the force applied to attract items. It's calculated based on `distance_full`, capped at 20.
*   `items`: A table containing the entity IDs of all "gold\_nugget" entities found in the game world.
*   `distance`: The Manhattan distance (sum of absolute differences in x and y) between the player and an item.
*   `direction`: The angle in radians pointing from the item towards the player.
*   `vel_x`, `vel_y`: The calculated velocity components to apply to the item's physics body.

## Logic Flow

The script first retrieves the player's current position (`x`, `y`) and the global attraction range. It then iterates through all identified gold nuggets. For each nugget:

1.  It calculates the Manhattan distance.
2.  If the distance is within a slightly larger range (`distance_full * 1.25`), it proceeds to calculate the Euclidean distance and the direction towards the player.
3.  If the Euclidean distance is within the primary attraction range (`distance_full`), it retrieves the item's `PhysicsBodyComponent`.
4.  Finally, it calculates and applies a force to the item's physics body, moving it towards the player.

```lua
--[[
	Attracts nearby gold nuggets towards the player.
]]
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local items = EntityGetWithTag( "gold_nugget" )
local distance_full = tonumber( GlobalsGetValue( "PERK_ATTRACT_ITEMS_RANGE", "72" ) )
local power = math.min( distance_full / 8, 20 )

if ( #items > 0 ) then
	for i,item_id in ipairs(items) do	
		local px, py = EntityGetTransform( item_id )
		
		local distance = math.abs( x - px ) + math.abs( y - py )
		
		if ( distance < distance_full * 1.25 ) then
			distance = math.sqrt( ( x - px ) ^ 2 + ( y - py ) ^ 2 )
			direction = 0 - math.atan2( ( y - py ), ( x - px ) )
	
			if ( distance < distance_full ) then
				local physicscomponents = EntityGetComponent( item_id, "PhysicsBodyComponent" )
				
				if ( physicscomponents ~= nil ) then
					local vel_x = math.cos( direction ) * power
					local vel_y = 0 - math.sin( direction ) * power
					
					PhysicsApplyForce( item_id, vel_x, vel_y )
				end
			end
		end
	end
end
```