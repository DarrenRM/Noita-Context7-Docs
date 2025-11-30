---
title: WASD Controls Trigger
category: scripts
---

# WASD Controls Trigger

This script defines a collision trigger that enables components on an entity tagged with "controls_wasd" when a collision occurs. This is typically used to activate WASD movement controls when the player enters a specific area.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. It is designed to be called when a collision event is detected.

1.  **Finds Closest Entity:** It searches for the closest entity that has the tag "controls_wasd".
2.  **Retrieves Components:** It then retrieves all components associated with that found entity.
3.  **Enables Components:** Finally, it iterates through all retrieved components and enables them.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

function collision_trigger()
	-- Find the closest entity with the "controls_wasd" tag
	local entity_id = EntityGetClosestWithTag( 275, -120, "controls_wasd" )
	
	-- If no such entity is found, exit the function
	if entity_id == nil then
		return
	end

	-- Get all components of the found entity
	local components = EntityGetAllComponents( entity_id )
	
	-- If the entity has no components, exit the function
	if components == nil then
		return
	end

	-- Iterate through all components and enable them
	for i,comp in ipairs( components ) do 
		EntitySetComponentIsEnabled( entity_id, comp, true )
	end
end
```