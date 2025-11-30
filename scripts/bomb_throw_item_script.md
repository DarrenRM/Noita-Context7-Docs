---
title: Bomb Throw Item Script
category: scripts
---

---

# Bomb Throw Item Script

This script defines the behavior for an item that, when thrown, enables a timer component on the entity.

## Core Functionality

### `throw_item(from_x, from_y, to_x, to_y)`

This function is called when the item is thrown.

*   **`from_x`, `from_y`**: The starting coordinates of the throw.
*   **`to_x`, `to_y`**: The target coordinates of the throw.

#### Key Actions:

1.  **Get Entity ID**: Retrieves the unique identifier for the entity being acted upon.
2.  **Enable Timer**: Activates the "timer" component associated with the entity.
3.  **Remove Item Component**: Removes the `ItemComponent` from the entity. This is likely to prevent the item from being re-used or to transition it to a different state after being thrown.

```lua
function throw_item( from_x, from_y, to_x, to_y )
	local entity_id = GetUpdatedEntityID()

	EntitySetComponentsWithTagEnabled( entity_id, "timer", true )

	edit_component( entity_id, "ItemComponent", function( comp, vars )
		EntityRemoveComponent( entity_id, comp)
	end)
end
```