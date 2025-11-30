---
title: Worm Bigger Holes Perk
category: scripts
---

# Worm Bigger Holes Perk

This script modifies the behavior of "worm" entities when the "Worm Bigger Holes" perk is active. It doubles the effective radius of the worm's hitbox, ground check, and cell-eating capabilities, and ensures it eats more than just stains.

## Key Functionality

*   **Targeting Worms:** The script identifies all entities with the "worm" tag.
*   **Perk Activation Check:** It checks if the "worm_bigger_holes" perk has already been applied to a worm using a `VariableStorageComponent`.
*   **Component Addition:** If the perk is not yet active for a specific worm, it adds a `VariableStorageComponent` with the name "worm_bigger_holes" and a corresponding tag.
*   **Cell Eater Enablement:** It enables the "cell\_eater" component for the worm.
*   **Radius Modification:**
    *   Doubles the `hitbox_radius` and `ground_check_offset` of the `WormComponent`.
    *   Doubles the `radius` of the `CellEaterComponent`.
*   **Cell Eater Behavior:** Sets `only_stain` to `false` for the `CellEaterComponent`, allowing the worm to eat more than just stains.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Find all entities tagged as "worm"
local targets = EntityGetWithTag( "worm" )

-- Proceed only if there are any worms found
if ( #targets > 0 ) then
	-- Iterate through each worm entity
	for i,target_id in ipairs( targets ) do
		-- Check if the "worm_bigger_holes" perk is already applied
		local variablestorages = EntityGetComponent( target_id, "VariableStorageComponent", "worm_bigger_holes" )
		local found = false
		
		if ( variablestorages ~= nil ) then
			found = true
		end
		
		-- If the perk is not found, apply it
		if ( found == false ) then
			-- Add a VariableStorageComponent to mark the perk as applied
			local cid = EntityAddComponent( target_id, "VariableStorageComponent", 
			{ 
				name = "worm_bigger_holes",
			} )
			ComponentAddTag( cid, "worm_bigger_holes" )
			
			-- Enable the cell eater component
			EntitySetComponentsWithTagEnabled( target_id, "cell_eater", true )
			
			-- Modify the WormComponent
			edit_component( target_id, "WormComponent", function(comp,vars)
				local radius = ComponentGetValue2( comp, "hitbox_radius" )
				local radius2 = ComponentGetValue2( comp, "ground_check_offset" )
				-- Double the radii
				radius = radius * 2.0
				radius2 = radius2 * 2.0
				ComponentSetValue2( comp, "hitbox_radius", radius )
				ComponentSetValue2( comp, "ground_check_offset", radius2 )
			end)
			
			-- Modify the CellEaterComponent
			edit_component( target_id, "CellEaterComponent", function(comp,vars)
				local radius = ComponentGetValue2( comp, "radius" )
				-- Double the radius
				radius = radius * 2.0
				ComponentSetValue2( comp, "radius", radius )
				-- Allow eating more than just stains
				ComponentSetValue2( comp, "only_stain", false )
			end)
		end
	end
end
```