---
title: Necrobot End Status Effect
category: scripts
---

---

# Necrobot End Status Effect

This script handles the termination of a "necrobot" entity in Noita. When this status effect is applied, it triggers the destruction of the current entity and potentially loads a new entity based on a stored file path.

## Key Functionality

*   **Entity Cleanup:** The primary function is to remove the entity that has this status effect applied.
*   **Conditional Entity Loading:** If the necrobot entity has a `VariableStorageComponent` with the key `necrobot_entity_file`, the script will load a new entity from the specified file at the necrobot's current position.
*   **Particle Effect:** A "poof\_green\_sparse" particle effect is spawned at the necrobot's location upon termination.
*   **Component Addition:** The newly loaded entity (if any) will have a `VariableStorageComponent` added with the tag `no_gold_drop`.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Loads utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the ID of the entity this script is attached to.
local x,y = EntityGetTransform( entity_id ) -- Retrieves the current position (x, y) of the entity.

-- Attempts to find a VariableStorageComponent with the specific key "necrobot_entity_file".
local comp = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "necrobot_entity_file" )

if ( comp ~= nil ) then -- Checks if the component was found.
	local file = ComponentGetValue2( comp, "value_string" ) -- Retrieves the file path stored in the component.
	
	if ( file ~= nil ) and ( #file > 0 ) then -- Checks if a valid file path was retrieved.
		local eid = EntityLoad( file, x, y ) -- Loads a new entity from the stored file path at the current position.
		EntityLoad( "data/entities/particles/poof_green_sparse.xml", x, y ) -- Spawns a green poof particle effect.
		
		-- Adds a VariableStorageComponent to the newly loaded entity.
		EntityAddComponent( eid, "VariableStorageComponent", 
		{ 
			_tags="no_gold_drop", -- Ensures the new entity does not drop gold.
		} )
	end
end

EntityKill( entity_id ) -- Destroys the original entity that had this status effect.
```