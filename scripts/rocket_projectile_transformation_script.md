---
title: Rocket Projectile Transformation Script
category: scripts
---

---

# Rocket Projectile Transformation Script

This script modifies existing projectiles in Noita, transforming them into various rocket types under specific conditions. It's designed to be attached to an entity that will periodically scan for projectiles and apply transformations.

## Core Functionality

The script iterates through all entities tagged as "projectile". If a projectile does not have the "rocket" tag, it undergoes a transformation.

### Key Transformations Applied:

*   **Explosion Prevention:** The script explicitly disables `on_death_explode` and `on_lifetime_out_explode` for the projectile's `ProjectileComponent`. This ensures that the original projectile doesn't explode before being transformed.
*   **Velocity Preservation:** The script reads the current velocity (`vel_x`, `vel_y`) of the projectile using its `VelocityComponent`.
*   **Random Rocket Selection:** A random rocket type is chosen from a predefined list: "rocket", "rocket_tier_2", and "rocket_tier_3".
*   **Projectile Replacement:** The original projectile is replaced with the selected rocket type using the `shoot_projectile_from_projectile` function. The new rocket inherits the position and velocity of the original projectile.
*   **Original Projectile Removal:** The original projectile is then destroyed using `EntityKill`.

## Script Logic Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Imports utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the ID of the entity running this script.
local x, y = EntityGetTransform( entity_id ) -- Gets the position of the script's entity (though not directly used for transformation).

local projectiles = EntityGetWithTag( "projectile" ) -- Retrieves all entities tagged as "projectile".

if ( #projectiles > 0 ) then -- Checks if any projectiles exist.
	for i,projectile_id in ipairs( projectiles ) do -- Loops through each projectile.
		local tags = EntityGetTags( projectile_id ) -- Gets the tags of the current projectile.
		
		if ( tags == nil ) or ( string.find( tags, "rocket" ) == nil ) then -- Condition: If the projectile has no tags or doesn't contain "rocket".
			local px, py = EntityGetTransform( projectile_id ) -- Gets the projectile's position.
			local vel_x, vel_y = 0,0 -- Initializes velocity variables.
			
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" ) -- Gets ProjectileComponents.
			local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" ) -- Gets VelocityComponents.
			
			if ( projectilecomponents ~= nil ) then -- If ProjectileComponents exist:
				for j,comp_id in ipairs( projectilecomponents ) do -- Loops through each ProjectileComponent.
					ComponentSetValue( comp_id, "on_death_explode", "0" ) -- Disables explosion on death.
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" ) -- Disables explosion when lifetime ends.
				end
			end
			
			if ( velocitycomponents ~= nil ) then -- If VelocityComponents exist:
				edit_component( projectile_id, "VelocityComponent", function(comp,vars) -- Edits the VelocityComponent.
					vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity", vel_x, vel_y) -- Reads the current velocity.
				end)
			end
			
			SetRandomSeed( px, py - 53 ) -- Sets a random seed based on projectile position for consistent randomness.
			local opts = { "rocket", "rocket_tier_2", "rocket_tier_3" } -- Array of possible rocket types.
			local rnd = Random( 1, #opts ) -- Selects a random index from the opts array.
			local opt = opts[rnd] -- Gets the chosen rocket type string.
			
			shoot_projectile_from_projectile( projectile_id, "data/entities/projectiles/deck/" .. opt .. ".xml", px, py, vel_x, vel_y ) -- Shoots the new rocket.
			EntityKill( projectile_id ) -- Destroys the original projectile.
		end
	end
end
```

## Key Components and Attributes Modified

*   **`ProjectileComponent`**:
    *   `on_death_explode`: Set to `"0"` to prevent explosions upon projectile death.
    *   `on_lifetime_out_explode`: Set to `"0"` to prevent explosions when the projectile's lifetime expires.
*   **`VelocityComponent`**:
    *   `mVelocity`: The existing velocity of the projectile is read and preserved for the new rocket.
*   **`shoot_projectile_from_projectile` function**:
    *   This is the core function for replacing the projectile. It takes the original projectile's ID, the XML path to the new projectile, its position, and its velocity.
*   **Randomization**:
    *   `SetRandomSeed`: Used to ensure that the random selection of rocket types is consistent for projectiles at similar locations.
    *   `Random`: Used to pick an index from the `opts` table.

## Usage Notes

*   This script is intended to be attached to an entity that will exist in the game world and periodically execute this logic.
*   The script relies on the presence of entities with the "projectile" tag.
*   The transformation only occurs if the projectile *does not* already have the "rocket" tag.
*   The specific rocket types are defined by their XML files located in `data/entities/projectiles/deck/`.