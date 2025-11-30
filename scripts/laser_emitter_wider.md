---
title: Laser Emitter Wider
category: scripts
---

# Laser Emitter Wider

This script modifies existing `LaserEmitterComponent`s on an entity. It increases the `beam_radius`, `damage_to_entities`, and `max_length` of the laser.

## Key Attributes Modified

The script iterates through all `LaserEmitterComponent`s attached to the entity and applies the following modifications:

*   **`beam_radius`**: Increased by `2.0`. This directly affects the width of the laser beam.
*   **`damage_to_entities`**: Increased by `0.025`. This adds a small amount of damage to the laser's impact.
*   **`max_length`**: Increased by `36`. This extends the maximum range of the laser beam.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Get the root entity to ensure modifications apply correctly
entity_id = EntityGetRootEntity( entity_id )

if ( entity_id ~= NULL_ENTITY ) then
	-- Retrieve all LaserEmitterComponent components
	local comps = EntityGetComponent( entity_id, "LaserEmitterComponent" )
	
	if ( comps ~= nil ) then
		-- Iterate through each found component
		for i,comp in ipairs( comps ) do
			-- Get current values
			local width = ComponentObjectGetValue2( comp, "laser", "beam_radius" ) or 0
			local dmg = ComponentObjectGetValue2( comp, "laser", "damage_to_entities" ) or 0
			local length = ComponentObjectGetValue2( comp, "laser", "max_length" ) or 0
			
			-- Apply modifications
			width = width + 2.0
			dmg = dmg + 0.025
			length = length + 36
			
			-- Set the modified values back to the component
			ComponentObjectSetValue2( comp, "laser", "beam_radius", width )
			ComponentObjectSetValue2( comp, "laser", "damage_to_entities", dmg )
			ComponentObjectSetValue2( comp, "laser", "max_length", length )
		end
	end
end
```