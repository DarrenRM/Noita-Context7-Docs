---
title: Racing Cart Driver Check
category: scripts
---

---

# Racing Cart Driver Check

This script is responsible for checking for a "small_friend" entity within a radius of the racing cart. If a suitable friend is found, it will be "killed" (removed from play), and the racing cart will gain the "driver" component and the "small_friend" tag, indicating it now has a driver.

## Key Functionality

*   **Proximity Check:** Detects entities with the "small_friend" tag within a 20-unit radius of the racing cart.
*   **Driver Assignment:** If a "small_friend" is found and is not "polymorphed," it is removed.
*   **Cart State Update:**
    *   Enables the "driver" component on the racing cart.
    *   Disables the "driverless" component on the racing cart.
    *   Adds the "small_friend" tag to the racing cart.

## Lua Script Logic

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Check for entities with the "small_friend" tag within a 20-unit radius
local targets = EntityGetInRadiusWithTag( x, y, 20, "small_friend" )

-- If any targets are found
if ( #targets > 0 ) then
	for i,t in ipairs( targets ) do
		-- Ensure the target is not polymorphed
		if ( EntityHasTag( t, "polymorphed") == false ) then
			-- Remove the target entity
			EntityKill( t )
			
			-- Enable the "driver" component on the racing cart
			EntitySetComponentsWithTagEnabled( entity_id, "driver", true )
			-- Disable the "driverless" component on the racing cart
			EntitySetComponentsWithTagEnabled( entity_id, "driverless", false )
			
			-- Add the "small_friend" tag to the racing cart
			EntityAddTag( entity_id, "small_friend" )
			
			-- Exit the loop and script execution once a driver is assigned
			return
		end
	end
end
```