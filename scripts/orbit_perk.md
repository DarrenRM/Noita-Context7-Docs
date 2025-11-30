---
title: Orbit Perk
category: scripts
---

# Orbit Perk

This script implements the "Orbit" perk in Noita. When active, it causes projectiles fired by the player to orbit around the player's current position under certain conditions.

## Core Functionality

The perk targets projectiles within a radius of the player and modifies their behavior.

### Key Attributes and Logic

*   **Targeting Projectiles:** The script identifies projectiles within a 12-unit radius of the player's current position.
*   **Excluding Player's Own Projectiles:** It checks if the projectile was shot by the player entity itself. If so, it's ignored.
*   **Speed Threshold:** Projectiles with a speed less than 1000 units are considered for the orbit effect.
*   **Luck-Based Activation:** A random chance (50% chance, based on `Random(1, 2) > 1`) determines if the orbit effect is applied.
*   **Orbital Trajectory Calculation:**
    *   Calculates the current direction of the projectile.
    *   Calculates the direction from the player to the projectile.
    *   Determines a "mirror" angle based on the projectile's direction.
    *   Calculates a "final" angle by adding the difference between the mirror and projectile direction to the mirror angle. This creates a tangential orbit.
*   **Position Adjustment:** The projectile's position is adjusted to be 24 units away from the player along the calculated `final` orbital path.
*   **Transform Update:** The projectile's transform (position) is updated to its new orbital location.

### Code Snippets

```lua
-- Get player's position
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Find projectiles within radius
local projectiles = EntityGetInRadiusWithTag( x, y, 12, "projectile" )

-- Iterate through found projectiles
for i,projectile_id in ipairs(projectiles) do
	local px, py = EntityGetTransform( projectile_id )
	local vel_x, vel_y = 0,0
	local who_shot = 0

	-- Get projectile velocity
	edit_component( projectile_id, "VelocityComponent", function(comp,vars)
		vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
	end)

	-- Get who shot the projectile
	edit_component( projectile_id, "ProjectileComponent", function(comp,vars)
		who_shot = ComponentGetValue2( comp, "mWhoShot" )
	end)

	-- Check if projectile was NOT shot by the player
	if ( who_shot ~= entity_id ) then
		local spd = math.sqrt( vel_y ^ 2 + vel_x ^ 2 )

		-- Check speed threshold
		if ( spd < 1000 ) then
			local luck = Random( 1, 2 )

			-- Apply orbit effect with 50% chance
			if ( luck > 1 ) then
				-- Calculate orbital angles
				local dir = 0 - math.atan2( vel_y, vel_x )
				local dir2 = 0 - math.atan2( py - y, px - x )
				local mirror = dir + math.pi * 0.5
				local final = mirror + ( mirror - dir2 )

				-- Calculate new position
				px = x + math.cos( final ) * 24
				py = y - math.sin( final ) * 24

				-- Update projectile position
				EntitySetTransform( projectile_id, px, py )
			end
		end
	end
end
```