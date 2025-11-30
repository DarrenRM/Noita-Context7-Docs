---
title: Controls I Trigger Logic
category: guides
---

-- This script defines a function to enable all components of an entity with the tag "controls_i".
-- It's likely used in conjunction with a collision trigger to activate specific game mechanics or entities.

function collision_trigger()
	-- Find the closest entity with the tag "controls_i" near the current position.
	local entity_id = EntityGetClosestWithTag( 711, -112, "controls_i" )
	
	-- If no such entity is found, exit the function.
	if entity_id == nil then
		return
	end

	-- Get all components attached to the found entity.
	local components = EntityGetAllComponents( entity_id )
	-- If the entity has no components, exit the function.
	if components == nil then
		return
	end

	-- Iterate through all components and enable them.
	for i,comp in ipairs( components ) do 
		EntitySetComponentIsEnabled( entity_id, comp, true )
	end
end
```

---
title: Controls I Trigger Logic
category: scripts
---

# Controls I Trigger Logic

This script provides a function, `collision_trigger`, designed to be activated by in-game events (likely collisions). Its primary purpose is to locate and enable all components of a specific entity tagged with `"controls_i"`.

## Key Functionality

*   **Entity Identification:** The `collision_trigger` function searches for the nearest entity possessing the tag `"controls_i"`. This tag is crucial for identifying the target entity that will have its components manipulated.
*   **Component Enumeration:** Once the target entity is found, the script retrieves all of its attached components.
*   **Component Activation:** The core action of the script is to iterate through each of these components and set their enabled state to `true`. This effectively activates or re-activates the functionality associated with those components.

## Usage Context

This script is intended to be used as part of a larger modding system where a collision or other trigger event can be linked to the execution of the `collision_trigger` function. This allows for dynamic activation of game elements or mechanics based on player interaction or environmental changes.

## Important Notes

*   The coordinates `711, -112` in `EntityGetClosestWithTag` are hardcoded and likely represent a specific location or offset relevant to the mod's design.
*   The script assumes that the entity with the `"controls_i"` tag will have components that can be enabled or disabled.
*   Error handling is minimal; the script exits gracefully if the target entity or its components are not found.