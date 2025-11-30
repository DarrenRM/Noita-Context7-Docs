---
title: Projectile Death Cross Transformation
category: scripts
---

# Projectile Death Cross Transformation

This script modifies existing projectiles in Noita by transforming them into "death crosses" upon their destruction or when their lifetime expires. It randomly selects between a standard "death_cross" and a "death_cross_big" variant.

## Key Functionality

This script iterates through all entities tagged as "projectile". For each projectile that does *not* already have the "death_cross" tag, it performs the following actions:

1.  **Disables Explosions:** It disables any `on_death_explode` and `on_lifetime_out_explode` behaviors on the projectile's `ProjectileComponent`.
2.  **Random Selection:** It randomly chooses between two death cross projectile types: `"death_cross"` or `"death_cross_big"`.
3.  **Spawns Death Cross:** It spawns the selected death cross projectile at the original projectile's location.
4.  **Kills Original Projectile:** It then destroys the original projectile.

## Core Logic

The script uses a loop to check each projectile and applies transformations based on specific conditions.

### `all_deathcrosses.lua`

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local projectiles = EntityGetWithTag( "projectile" )

if ( #projectiles > 0 ) then
	for i,projectile_id in ipairs( projectiles ) do
		local tags = EntityGetTags( projectile_id )
		
		-- Check if the projectile is NOT already a death cross
		if ( tags == nil ) or ( string.find( tags, "death_cross" ) == nil ) then
			local px, py = EntityGetTransform( projectile_id )
			
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" )
			local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" )
			
			-- Disable death/lifetime explosions for the original projectile
			if ( projectilecomponents ~= nil ) then
				for j,comp_id in ipairs( projectilecomponents ) do
					ComponentSetValue( comp_id, "on_death_explode", "0" )
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )
				end
			end
			
			-- Set random seed for variety
			SetRandomSeed( px, py - 543 )
			
			-- Randomly select between death_cross and death_cross_big
			local opts = { "death_cross", "death_cross_big" }
			local rnd = Random( 1, #opts )
			local opt = opts[rnd]
			
			-- Spawn the selected death cross projectile
			shoot_projectile_from_projectile( projectile_id, "data/entities/projectiles/deck/" .. opt .. ".xml", px, py, 0, 0 )
			
			-- Kill the original projectile
			EntityKill( projectile_id )
		end
	end
end
```

## Key Components and Attributes

*   **`EntityGetWithTag("projectile")`**: Retrieves all entities currently tagged as "projectile".
*   **`EntityGetTags(projectile_id)`**: Gets the tags associated with a specific projectile entity.
*   **`string.find(tags, "death_cross")`**: Checks if the "death\_cross" tag exists within the projectile's tags.
*   **`EntityGetComponent(projectile_id, "ProjectileComponent")`**: Retrieves the `ProjectileComponent` of a projectile.
*   **`ComponentSetValue(comp_id, "on_death_explode", "0")`**: Disables the explosion effect when the projectile dies.
*   **`ComponentSetValue(comp_id, "on_lifetime_out_explode", "0")`**: Disables the explosion effect when the projectile's lifetime expires.
*   **`SetRandomSeed(px, py - 543)`**: Initializes the random number generator based on the projectile's position for more deterministic randomness.
*   **`Random(1, #opts)`**: Generates a random integer within the range of the `opts` table.
*   **`opts = { "death_cross", "death_cross_big" }`**: A table containing the names of the death cross projectile variants to choose from.
*   **`shoot_projectile_from_projectile(...)`**: A utility function (likely from `utilities.lua`) that spawns a new projectile originating from another projectile.
*   **`EntityKill(projectile_id)`**: Destroys the specified entity.