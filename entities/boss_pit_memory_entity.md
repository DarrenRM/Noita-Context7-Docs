---
title: Boss Pit Memory Entity
category: entities
---

# Boss Pit Memory Entity

This entity is responsible for the "memory" of the Boss Pit, specifically tracking what projectiles it has encountered. This information is likely used to influence its behavior or attacks.

## Key Components and Functionality

### Pathfinding Component (`PathFindingComponent`)

*   **Purpose:** Manages the entity's pathfinding capabilities.
*   **Key Attribute:** `read_state` - Indicates the current state of the pathfinding.
*   **Logic:** The script checks if the `read_state` is low (implying the entity might be stuck). If so, it increments a counter (`frames_stuck`) stored in a `VariableStorageComponent`. If the entity is not stuck, the counter is reset. A high `frames_stuck` value suggests the boss is stuck.

### Variable Storage Component (`VariableStorageComponent`)

*   **Purpose:** Stores custom variables for entities.
*   **Key Variables:**
    *   `pathfinding_frames_stuck` (integer): Counts consecutive frames where the entity's pathfinding state indicates it might be stuck.
    *   `memory` (string): Stores the filename of the last projectile encountered.
    *   `projectile_file` (string): Used within projectile entities to store their filename.

### Projectile Detection and Memory Update

*   **Logic:** The script scans for any entities tagged as "projectile" within a 64-unit radius of the boss pit.
*   **Memory Update:** If a projectile is found, its `projectile_file` (stored in its `VariableStorageComponent`) is retrieved. This filename is then stored in the boss pit's `memory` variable within its own `VariableStorageComponent`. This effectively "remembers" the last projectile it interacted with.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( GetUpdatedEntityID() )

-- Pathfinding state check and 'frames_stuck' counter
local pf_comp = EntityGetFirstComponent( entity_id, "PathFindingComponent")
if( pf_comp ) then
	local pf_state = ComponentGetValue2( pf_comp, "read_state" )

	local comps = EntityGetComponent( entity_id, "VariableStorageComponent" )
	if ( comps ~= nil ) then
		for i,v in ipairs( comps ) do
			local n = ComponentGetValue2( v, "name" )
			if( n == "pathfinding_frames_stuck" ) then
				local frames_stuck = ComponentGetValue2( v, "value_int" )
				if( pf_state <= 1 ) then -- If pathfinding state suggests stuck
					frames_stuck = frames_stuck + 1
				else
					frames_stuck = 0 -- Reset if not stuck
				end
				ComponentSetValue2( v, "value_int", frames_stuck )
				-- NOTE( Petri ): if frames_stuck is like higher than 160 it means the boss is stuck
				-- print( "frames_stuck: " .. tostring( frames_stuck ) )
			end
		end
	end
end

-- Projectile detection and memory update
local projectiles = EntityGetInRadiusWithTag( x, y, 64, "projectile" )

if ( #projectiles > 0 ) then
	local p = projectiles[1] -- Get the first projectile found
	local p_n = ""
	local comps = EntityGetComponent( p, "VariableStorageComponent" )
	if ( comps ~= nil ) then
		for i,v in ipairs( comps ) do
			local n = ComponentGetValue2( v, "name" )
			if ( n == "projectile_file" ) then
				p_n = ComponentGetValue2( v, "value_string" ) -- Get projectile filename
			end
		end
	end

	if ( #p_n > 0 ) then
		comps = EntityGetComponent( entity_id, "VariableStorageComponent" )
		if ( comps ~= nil ) then
			for i,v in ipairs( comps ) do
				local n = ComponentGetValue2( v, "name" )
				if ( n == "memory" ) then
					ComponentSetValue2( v, "value_string", p_n ) -- Store projectile filename in boss memory
					break
				end
			end
		end
	end
end
```