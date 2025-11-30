---
title: Projectile Eater Perk
category: scripts
---

# Projectile Eater Perk

This script defines the behavior for the "Projectile Eater" perk in Noita. When active, it allows the player to absorb incoming projectiles within a certain radius and angle.

## Core Functionality

The perk operates by:
1.  Identifying the player entity and its current aiming direction.
2.  Scanning for "projectile" entities within a defined radius.
3.  For each projectile found, it calculates the distance and direction relative to the player.
4.  If a projectile is within range and its trajectory is close to the player's aiming vector, the projectile is destroyed.

## Key Attributes & Elements

*   **`distance_full`**: Defines the maximum radius (in pixels) around the player within which projectiles will be considered for absorption.
*   **`mAimingVector`**: The player's aiming direction, used to determine the cone of projectile absorption.
*   **`projectile` tag**: Entities tagged with "projectile" are the targets for absorption.
*   **`dirdelta_deg < 24.0`**: This condition checks if the projectile's direction is within 24 degrees of the player's aiming direction.
*   **`EntityKill( projectile_id )`**: This function destroys the projectile if it meets the absorption criteria.
*   **`ComponentSetValue( comp_id, "on_death_explode", "0" )` and `ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )`**: These lines prevent projectiles from exploding upon death or when their lifetime expires, ensuring a clean absorption.

## Code Structure

```lua
-- Utility function to get updated entity ID
dofile_once("data/scripts/lib/utilities.lua")

-- Get the player entity and its transform
local entity_id = GetUpdatedEntityID()
local player_id = EntityGetRootEntity( entity_id )
local x, y = EntityGetTransform( entity_id )

-- Define the absorption radius
local distance_full = 24

-- Initialize aiming vector components
local ax = 0
local ay = 0

-- Find all projectiles within the absorption radius
local projectiles = EntityGetInRadiusWithTag( x, y, distance_full, "projectile" )

-- Get the player's aiming vector
edit_component( player_id, "ControlsComponent", function(comp,vars)
	ax,ay = ComponentGetValue2( comp, "mAimingVector" )
end)

-- Calculate the player's aiming angle
local a = math.pi - math.atan2( ay, ax )

-- Set the entity's transform to align with aiming (visual cue, not functional for absorption)
EntitySetTransform( entity_id, x, y, 0 - a )

-- Iterate through found projectiles
if ( #projectiles > 0 ) then
	for i,projectile_id in ipairs(projectiles) do
		-- Get projectile's position
		local px, py = EntityGetTransform( projectile_id )

		-- Calculate distance and direction to the projectile
		local distance = get_distance( px, py, x, y )
		local direction = get_direction( px, py, x, y )

		-- Calculate the angular difference between player aim and projectile direction
		local dirdelta = get_direction_difference( direction, a )
		local dirdelta_deg = math.abs( math.deg( dirdelta ) )

		-- Check if projectile is within range and within the aiming cone
		if ( distance < distance_full ) and ( dirdelta_deg < 24.0 ) then
			-- Get ProjectileComponent to modify its behavior
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" )

			if ( projectilecomponents ~= nil ) then
				for j,comp_id in ipairs(projectilecomponents) do
					-- Disable explosions on death or lifetime out
					ComponentSetValue( comp_id, "on_death_explode", "0" )
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )
				end
			end

			-- Destroy the projectile
			EntityKill( projectile_id )
		end
	end
end
```