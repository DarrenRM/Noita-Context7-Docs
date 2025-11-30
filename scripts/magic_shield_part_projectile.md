---
title: Magic Shield Part Projectile
category: scripts/
---

# Magic Shield Part Projectile

This script defines the behavior for a projectile that acts as a part of a magic shield. It manages its rotation, position relative to its owner, and its eventual destruction if the owner is no longer valid.

## Key Attributes

The script primarily interacts with and modifies the following attributes:

*   **`angle`**: Stores the current rotational angle of the shield part. This is dynamically updated based on its initial value and rotation speed.
*   **`rotation`**: Represents the rotational speed or increment applied to the `angle` each frame.
*   **`owner_id`**: The entity ID of the projectile's owner. This is crucial for positioning and determining the shield part's lifespan.
*   **`length`**: The distance from the owner's center at which the shield part is positioned.

## Core Logic

### Initialization and Variable Storage

The script first retrieves the entity's ID and then accesses its `VariableStorageComponent`. It iterates through the stored variables to find and assign values to `angle`, `rotation`, and `owner_id`.

```lua
local entity_id = GetUpdatedEntityID()
local angle = 0
local rotation = 0
local owner_id = 0
local length = 16

local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )
if ( variablestorages ~= nil ) then
	local anglestorage -- To store the specific storage ID for angle
	
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
	
	-- Update angle based on rotation speed
	angle = angle + rotation * 0.02
	ComponentSetValue2( anglestorage, "value_float", angle )
end
```

### Positional Update

The shield part's position is calculated based on its owner's transform and its own `angle` and `length`.

1.  **Get Owner's Position**: It retrieves the `x` and `y` coordinates of the owner entity.
2.  **Calculate New Position**: Using trigonometry (`math.cos` and `math.sin`), it determines the shield part's new `px` and `py` coordinates, offset from the owner by `length` at the current `angle`.
3.  **Set Entity Transform**: The shield part's transform is updated to the newly calculated position.

```lua
angle = angle + rotation -- Apply final rotation for positioning

if ( owner_id ~= NULL_ENTITY ) then
	local x, y = EntityGetTransform( owner_id )
	
	if ( x ~= nil ) and ( y ~= nil ) then
		local px = x + math.cos( angle ) * length
		local py = y - math.sin( angle ) * length
		
		EntitySetTransform( entity_id, px, py )
	else
		-- If owner is invalid, destroy the shield part
		EntityKill( entity_id )
	end
end
```

### Owner Validation

If the `owner_id` is `NULL_ENTITY` (meaning the owner no longer exists), the shield part is immediately destroyed using `EntityKill( entity_id )`. This prevents orphaned projectiles from persisting in the game world.