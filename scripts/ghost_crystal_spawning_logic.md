---
title: Ghost Crystal Spawning Logic
category: scripts
---

# Ghost Crystal Spawning Logic

This script defines the logic for spawning a "ghost" entity when a specific building (likely a "ghost crystal") is activated or interacted with.

## Core Functionality

The primary function `spawn_ghost()` handles the creation and initialization of the ghost entity.

### Key Steps:

1.  **Get Entity ID and Position:** Retrieves the unique identifier and world coordinates of the entity that triggered the script.
2.  **Load Ghost Entity:** Loads the `ghost.xml` entity definition from `data/entities/animals/` at the current position.
3.  **Configure Ghost Component:**
    *   Iterates through all `GhostComponent`s of the newly spawned ghost.
    *   Sets the `mEntityHome` variable within the `GhostComponent` to the ID of the triggering entity. This likely establishes a link or ownership.
4.  **Store Ghost ID (Optional):**
    *   Checks if the triggering entity has a `VariableStorageComponent` with the key `"ghost_id"`.
    *   If found, it updates the `value_int` of this component to store the entity ID of the spawned ghost. This allows the triggering entity to reference or control the spawned ghost.

## Script Execution

The `spawn_ghost()` function is called directly at the end of the script, ensuring that a ghost is spawned when this script is executed.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function spawn_ghost()
	-- print( "spawning ghost" )
	local entity_id = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	local entity_ghost = EntityLoad( "data/entities/animals/ghost.xml", pos_x, pos_y )
	
	edit_all_components( entity_ghost, "GhostComponent", function(comp,vars)
		vars.mEntityHome = entity_id
	end)
	
	local comp = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "ghost_id" )
	
	if ( comp ~= nil ) then
		ComponentSetValue2( comp, "value_int", entity_ghost )
	end
end

spawn_ghost()
```