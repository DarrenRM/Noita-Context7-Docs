---
title: Controls F Trigger
category: guides
---

-- This script defines a function to trigger components on an entity with the tag "controls_f".
-- It's likely used in conjunction with a collision event to activate certain game mechanics.

function collision_trigger()
	-- Find the closest entity with the tag "controls_f" near the current position.
	local entity_id = EntityGetClosestWithTag( 671, -112, "controls_f" )

	-- If no such entity is found, exit the function.
	if entity_id == nil then
		return
	end

	-- Get all components attached to the found entity.
	local components = EntityGetAllComponents( entity_id )
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
title: Controls F Trigger
category: scripts
---

# Controls F Trigger

This script provides a function, `collision_trigger`, designed to activate components on an entity tagged with "controls_f". It's a common pattern for triggering in-game events or mechanics when a player interacts with a specific object or area.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. Its primary purpose is to:

1.  **Locate Target Entity**: It searches for the nearest entity that possesses the tag "controls_f". This tag acts as an identifier for the entity that should be affected.
2.  **Retrieve Components**: Once the target entity is found, it retrieves all components associated with that entity.
3.  **Enable Components**: It then iterates through each of these components and explicitly enables them. This means any functionality tied to these components will become active.

## Usage Example (Conceptual)

While the provided snippet only contains the `collision_trigger` function, it's intended to be called by another game system, most likely a collision detection system.

For instance, a collision component on a player or a specific object might call `collision_trigger()` when a collision occurs. This would then activate the components on the "controls_f" entity, potentially leading to:

*   Activating a switch.
*   Opening a door.
*   Triggering a visual or audio effect.
*   Initiating a new game state.

## Important Considerations for Modding

*   **Tagging**: Ensure that the entity you want to trigger has the "controls_f" tag. This is crucial for `EntityGetClosestWithTag` to find it.
*   **Component Management**: The script enables *all* components. If you only want to enable specific components, you would need to modify the loop to check component types or names before enabling them.
*   **Entity Placement**: The `EntityGetClosestWithTag` function uses coordinates (671, -112) as a reference point. In a modding context, this might be relative to the entity that *calls* the `collision_trigger` function, or it might be a fixed world coordinate. Understanding the context of where this function is called is key.