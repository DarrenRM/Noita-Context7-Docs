---
title: Projectile Slow Field Perk
category: scripts
---

# Projectile Slow Field Perk

This script implements a perk that creates a field around the player which slows down any projectiles entering it.

## Functionality

When the perk is active, the script periodically checks for projectiles within a specified radius around the player. If projectiles are found, their velocity is reduced.

### Key Attributes

*   **`distance_full`**: Defines the radius (in pixels) around the player within which projectiles will be affected. In this case, it's set to `66`.
*   **Velocity Reduction**: Projectiles within the radius have their `mVelocity` component reduced by multiplying their current X and Y components by `0.9`. This results in a 10% speed reduction.

### Core Logic

1.  **Get Player Position**: The script obtains the player's current entity ID and its X, Y coordinates.
2.  **Find Projectiles**: It searches for all entities tagged as "projectile" within the `distance_full` radius around the player.
3.  **Iterate and Slow**: If any projectiles are found:
    *   It iterates through each projectile.
    *   It retrieves the `VelocityComponent` for the projectile.
    *   If the component exists, it modifies the `mVelocity` vector, reducing both its X and Y components by 10%.

### Code Snippet Example

```lua
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )
local distance_full = 66 -- Radius of the slow field

local projectiles = EntityGetInRadiusWithTag( x, y, distance_full, "projectile" )

if ( #projectiles > 0 ) then
	for i,projectile_id in ipairs(projectiles) do	
		local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" )
		
		if ( velocitycomponents ~= nil ) then
			edit_component( projectile_id, "VelocityComponent", function(comp,vars)
				local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
				
				-- Reduce velocity by 10%
				vel_x = vel_x * 0.9
				vel_y = vel_y * 0.9

				ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
			end)
		end
	end
end
```