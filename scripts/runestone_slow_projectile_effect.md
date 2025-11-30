---
title: Runestone Slow Projectile Effect
category: scripts
---

# Runestone Slow Projectile Effect

This script defines the behavior for a runestone that slows down nearby projectiles. When activated, it targets projectiles within a radius and reduces their velocity.

## Key Functionality

### Projectile Detection and Slowing

*   **Radius:** Detects projectiles within a 192-unit radius.
*   **Targeting:** Identifies entities with the "projectile" tag.
*   **Velocity Modification:** For each detected projectile, it accesses its `VelocityComponent`.
*   **Speed Reduction:** Multiplies the projectile's current velocity (`mVelocity`) by 0.25, effectively slowing it down to 25% of its original speed.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Get all projectiles within a 192-unit radius
local projectiles = EntityGetInRadiusWithTag( x, y, 192, "projectile" )

-- Check if any projectiles were found
if ( #projectiles > 0 ) then
	-- Iterate through each detected projectile
	for i,projectile_id in ipairs( projectiles ) do
		local vel_x, vel_y = 0,0
		
		-- Get the VelocityComponent of the projectile
		local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" )
		
		-- If the VelocityComponent exists, modify it
		if ( velocitycomponents ~= nil ) then
			edit_component( projectile_id, "VelocityComponent", function(comp,vars)
				-- Get the current velocity
				vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity", vel_x, vel_y)
				
				-- Reduce velocity by 75%
				vel_x = vel_x * 0.25
				vel_y = vel_y * 0.25
				
				-- Set the new, slower velocity
				ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
			end)
		end
	end
end
```