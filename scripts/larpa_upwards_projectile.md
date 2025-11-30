---
title: Larpa Upwards Projectile
category: scripts
---

---

# Larpa Upwards Projectile

This script defines the behavior for a projectile that shoots another projectile upwards. It's designed to be attached to a projectile entity that has a `VariableStorageComponent` named "projectile_file" storing the path to the projectile to be fired.

## Key Attributes

*   **`projectile_file`**: A string value within a `VariableStorageComponent` that specifies the file path of the projectile to be spawned.

## Functionality

1.  **Initialization**:
    *   Retrieves the root entity ID and its position.
    *   Sets a random seed based on game frame and entity position.
2.  **Projectile File Retrieval**:
    *   Iterates through `VariableStorageComponent`s attached to the entity.
    *   If a component's `name` is "projectile_file", its `value_string` is stored in the `projectile_file` variable.
3.  **Projectile Spawning**:
    *   If `projectile_file` is not empty:
        *   Defines a fixed upward velocity (`vel_y = -1700`).
        *   Uses `shoot_projectile_from_projectile` to spawn the specified projectile from the current projectile's position with the defined upward velocity.
        *   Adds the tag "projectile\_cloned" to the newly spawned projectile.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = EntityGetRootEntity( GetUpdatedEntityID() )
local pos_x, pos_y = EntityGetTransform( entity_id )

SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )
local projectile_file = ""

if ( variablestorages ~= nil ) then
	for j,storage_id in ipairs(variablestorages) do
		local var_name = ComponentGetValue( storage_id, "name" )
		if ( var_name == "projectile_file" ) then
			projectile_file = ComponentGetValue2( storage_id, "value_string" )
		end
	end
end

if ( #projectile_file > 0 ) then
	local length = 1700

	local vel_x = 0
	local vel_y = 0 - length

	local eid = shoot_projectile_from_projectile( entity_id, projectile_file, pos_x, pos_y, vel_x, vel_y )
	EntityAddTag( eid, "projectile_cloned" )
end
```