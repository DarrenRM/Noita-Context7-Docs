---
title: Cordyceps Perk Logic
category: scripts
---

# Cordyceps Perk Logic

This script handles the logic for the Cordyceps perk in Noita. When activated, it searches for nearby entities with the "homing_target" tag. If found and the target entity does not already have the "cordyceps" or "polymorphed" tags, it applies the "cordyceps" tag and adds components to facilitate its behavior.

## Key Functionality

*   **Target Acquisition:** Detects entities within a 160-unit radius that are tagged as "homing_target".
*   **Tagging and Component Application:**
    *   Adds the "cordyceps" tag to eligible targets.
    *   Attaches a `VariableStorageComponent` named "cordyceps" to store perk-specific data.
    *   Attaches a `LuaComponent` that links to `cordyceps_death.lua` for handling the target's demise.

## Core Logic Breakdown

The script iterates through potential targets and applies the Cordyceps effect under specific conditions:

```lua
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Find entities within a radius that have the "homing_target" tag
local targets = EntityGetInRadiusWithTag( x, y, 160, "homing_target" )

if ( #targets > 0 ) then
	for i,target_id in ipairs( targets ) do
		-- Check if the target is not already tagged as "cordyceps" or "polymorphed"
		if ( EntityHasTag( target_id, "cordyceps" ) == false ) and ( EntityHasTag( target_id, "polymorphed") == false) then
			-- Apply the "cordyceps" tag
			EntityAddTag( target_id, "cordyceps" )
			
			-- Add a VariableStorageComponent for perk data
			EntityAddComponent( target_id, "VariableStorageComponent", 
			{ 
				name = "cordyceps",
			} )
			
			-- Add a LuaComponent to execute a death script
			EntityAddComponent( target_id, "LuaComponent", 
			{ 
				script_death = "data/scripts/perks/cordyceps_death.lua",
				execute_every_n_frame = "-1", -- This indicates the script is not meant to run continuously
			} )
		end
	end
end
```