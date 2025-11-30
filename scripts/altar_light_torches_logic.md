---
title: Altar Light Torches Logic
category: scripts
---

# Altar Light Torches Logic

This script defines the behavior for activating torches when an entity interacts with an altar.

## Core Functionality

The `collision_trigger` function is the main logic handler. It's designed to be called when an entity collides with the altar.

### Key Actions

1.  **Get Altar Position:** Retrieves the position of the entity that triggered the collision (the altar).
2.  **Find Torches:** Searches for all entities tagged with `"altar_torch"`.
3.  **Iterate and Activate:**
    *   Loops through each found torch.
    *   Checks if the torch is within a specific proximity of the altar (horizontal distance < 128, vertical distance < 64).
    *   If within range, it enables the `"fire"` component on the torch, causing it to light up.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")


function collision_trigger()

	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	local torches = EntityGetWithTag( "altar_torch" )

	if ( #torches > 0 ) then
		for index,torch in ipairs(torches) do
			if torch ~= nil then
				-- TODO: check distance to entity

				local tpos_x, tpos_y = EntityGetTransform( torch )
				if (math.abs( tpos_x-pos_x ) < 128 ) and (math.abs( tpos_y-pos_y ) < 64) then
					EntitySetComponentsWithTagEnabled( torch, "fire", true )
				end

			end
		end
	end
end
```

## Key Attributes/Elements

*   **`collision_trigger()`**: The primary function that executes the logic.
*   **`GetUpdatedEntityID()`**: Identifies the entity that initiated the event (the altar).
*   **`EntityGetTransform()`**: Retrieves the position of an entity.
*   **`EntityGetWithTag("altar_torch")`**: Finds all entities possessing the `"altar_torch"` tag.
*   **Proximity Check**:
    *   `math.abs( tpos_x-pos_x ) < 128`: Horizontal distance check.
    *   `math.abs( tpos_y-pos_y ) < 64`: Vertical distance check.
*   **`EntitySetComponentsWithTagEnabled( torch, "fire", true )`**: Activates the `"fire"` component on the torch, making it visible and active.