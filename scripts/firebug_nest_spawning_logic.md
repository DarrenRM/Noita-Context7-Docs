---
title: Firebug Nest Spawning Logic
category: scripts
---

# Firebug Nest Spawning Logic

This script defines the behavior for a "Firebug Nest" entity, primarily focusing on its ability to spawn Firebug enemies.

## Core Functionality

The script determines whether to spawn a new enemy based on a random chance and proximity to the player. It also limits the total number of spawned enemies to prevent excessive entity counts.

## Key Attributes and Logic

### Spawning Conditions

*   **Spawn Chance:** There's a 75% chance (`Random(0,100) < 75`) for the nest to attempt spawning an enemy on any given frame.
*   **Player Proximity:** The nest will only spawn an enemy if the player is within a `spawn_distance` of 200 units.
*   **Spawn Limit:** The nest will stop spawning enemies once 10 have been spawned (`spawned_entities < 10`).

### Enemy Selection

*   **Firebug:** 90% chance (`Random(1,10) < 9`) to spawn a regular `firebug.xml`.
*   **Big Firebug:** 10% chance (`Random(1,10) >= 9`) to spawn a `bigfirebug.xml`.

### Spawn Offset

Spawned enemies are placed with a small random offset (`Random(-4,4)`) from the nest's position to prevent them from overlapping perfectly.

### Lua Component Modification

When an enemy is spawned, its `LuaComponent` has its `script_death` variable set to an empty string. This likely prevents the spawned enemy from triggering any specific death-related Lua scripts.

## Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

if( Random(0,100) < 75 ) then -- 75% chance to attempt spawn
	local spawn_distance = 200
	local e_id = EntityGetClosestWithTag( pos_x, pos_y, "player_unit")

	if( e_id ~= 0 ) then
		local x, y = EntityGetTransform( e_id )
		local distance_sqrt = (x-pos_x)*(x-pos_x)+(y-pos_y)*(y-pos_y)
		if( distance_sqrt < spawn_distance * spawn_distance ) then -- Check player proximity
			local spawned_entities = GetValueInteger("spawned", 0)

			if (spawned_entities < 10) then -- Check spawn limit
				-- spawn enemy
				pos_x = pos_x + Random(-4,4)
				pos_y = pos_y + Random(-4,4)

				local new_entity = 0

				if (Random(1,10) < 9) then -- 90% chance for regular firebug
					new_entity = EntityLoad( "data/entities/animals/firebug.xml", pos_x, pos_y )
				else -- 10% chance for big firebug
					new_entity = EntityLoad( "data/entities/animals/bigfirebug.xml", pos_x, pos_y )
				end

				edit_component( new_entity, "LuaComponent", function(comp,vars)
					vars.script_death = "" -- Modify LuaComponent
				end)

				spawned_entities = spawned_entities + 1

				SetValueInteger("spawned", spawned_entities) -- Update spawned count
			end
		end
	end
end
```