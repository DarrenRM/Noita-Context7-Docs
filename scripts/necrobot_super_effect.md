---
title: Necrobot Super Effect
category: scripts
---

# Necrobot Super Effect

This script targets nearby "mortal" entities that are not the player or already tagged with "necrobot_NOT". For each qualifying entity, it applies a LuaComponent that triggers a specific death script (`necrobot_super.lua`) and spawns a small red spark particle effect. The target entity is then tagged with "necrobot_NOT" to prevent repeated application.

## Key Functionality

*   **Targeting:** Identifies entities within a `radius` of 144 units that have the "mortal" tag.
*   **Exclusions:** Ignores entities tagged as "player_unit" or "necrobot_NOT".
*   **Entity Type Check:** Filters targets to only include entities found within the `entities/animals/` directory.
*   **Status Effect Application:** Adds a `LuaComponent` to the target entity.
    *   `script_death`: Specifies `data/scripts/status_effects/necrobot_super.lua` to be executed upon the entity's death.
    *   `execute_every_n_frame`: Set to "-1", indicating the script is not intended for continuous frame-based execution but rather for an event (like death).
*   **Visual Effect:** Spawns a `tinyspark_red_sparse.xml` particle effect at the target's location.
*   **Preventing Re-application:** Adds the "necrobot_NOT" tag to the target entity to ensure it's only affected once.

## Core Logic Breakdown

The script iterates through potential targets and applies the "necrobot_NOT" tag to prevent multiple applications.

```lua
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )
local radius = 144

local targets = EntityGetInRadiusWithTag( x, y, radius, "mortal" )
local found = false -- This variable is declared but not used in the provided snippet.

for i,v in ipairs( targets ) do
	-- Check if the target is not the player and not already processed
	if ( EntityHasTag( v, "player_unit" ) == false ) and ( EntityHasTag( v, "necrobot_NOT" ) == false ) then
		local file = EntityGetFilename( v )
		
		-- Ensure it's a valid entity file and located in the animals directory
		if ( file ~= nil ) and ( #file > 0 ) and ( string.find( file, "entities/animals/" ) ~= nil ) then
			-- Apply the LuaComponent for the death effect
			EntityAddComponent( v, "LuaComponent", 
			{ 
				script_death = "data/scripts/status_effects/necrobot_super.lua",
				execute_every_n_frame = "-1",
			} )
			
			-- Spawn the visual particle effect
			local eid = EntityLoad( "data/entities/particles/tinyspark_red_sparse.xml", x, y )
			EntityAddChild( v, eid )
		end
		
		-- Mark the entity as processed
		EntityAddTag( v, "necrobot_NOT" )
	end
end
```