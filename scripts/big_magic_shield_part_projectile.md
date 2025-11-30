---
title: Big Magic Shield Part Projectile
category: scripts
---

# Big Magic Shield Part Projectile

This script defines the behavior for a projectile that acts as a part of a "big magic shield" in Noita. It manages its rotation, position relative to its owner, and its eventual destruction.

## Key Attributes and Behavior

### Rotation and Angle Management

*   **`angle`**: Stores the current rotational angle of the shield part. It's initialized from a `VariableStorageComponent` and updated based on `rotation`.
*   **`rotation`**: Represents a rotational offset, also stored in a `VariableStorageComponent`. This value influences the `angle` update.
*   The script dynamically updates the `angle` based on the `rotation` value, creating a rotating effect for the shield.

### Owner and Positioning

*   **`owner_id`**: Identifies the entity that "owns" this shield part. This is crucial for maintaining the shield's structure.
*   **`length`**: Defines the distance of the shield part from its owner.
*   The script retrieves the owner's position and calculates the shield part's new position using trigonometry (`math.cos`, `math.sin`) based on its `angle` and `length`.

### Entity Lifecycle

*   **`entity_id`**: The unique identifier for the current shield part entity.
*   **`EntityKill( entity_id )`**: Used to destroy the shield part if its owner is no longer valid (e.g., `owner_id` is `NULL_ENTITY` or the owner's transform is not found).
*   **`VariableStorageComponent`**: This component is used to store and retrieve the `angle`, `rotation`, and `owner_id` for the shield part.

## Lua Script Breakdown

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()

local angle = 0
local rotation = 0
local owner_id = 0
local length = 40 -- Distance from owner

-- Retrieve variables from VariableStorageComponent
local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )
if ( variablestorages ~= nil ) then
	local anglestorage -- To store the angle storage component for updates
	
	for j,storage_id in ipairs(variablestorages) do
		local var_name = ComponentGetValue( storage_id, "name" )
		if ( var_name == "angle" ) then
			angle = ComponentGetValue2( storage_id, "value_float" )
			anglestorage = storage_id
		elseif ( var_name == "rot" ) then
			rotation = ComponentGetValue2( storage_id, "value_int" )
		elseif ( var_name == "owner" ) then
			owner_id = ComponentGetValue2( storage_id, "value_int" )
		end
	end
	
	-- Update angle based on rotation
	angle = angle + rotation * 0.015
	
	-- Set the updated angle back to the storage
	ComponentSetValue2( anglestorage, "value_float", angle )
end

-- Apply rotation to the angle for positioning
angle = angle + rotation

-- Position the shield part relative to its owner
if ( owner_id ~= NULL_ENTITY ) then
	local x, y = EntityGetTransform( owner_id )
	
	if ( x ~= nil ) and ( y ~= nil ) then
		-- Calculate new position
		local px = x + math.cos( angle ) * length
		local py = y - math.sin( angle ) * length
		
		-- Set the entity's transform
		EntitySetTransform( entity_id, px, py )
	else
		-- Kill the entity if owner is invalid
		EntityKill( entity_id )
	end
end
```