---
title: Hearty End Status Effect
category: scripts
---

---

# Hearty End Status Effect

This script defines a status effect in Noita that modifies the player's maximum health.

## Effect Description

When the "effect_hearty" variable is set to a positive value, this status effect doubles the player's maximum health. The player's current health is then scaled proportionally to maintain their current health percentage.

## Key Attributes

*   **`effect_hearty`**: A float value stored in a `VariableStorageComponent`. If this value is greater than 0, the effect is triggered.
*   **`DamageModelComponent`**: The component targeted by this script to modify health values.
*   **`max_hp`**: The player's maximum health. This is doubled by the effect.
*   **`hp`**: The player's current health. This is adjusted to maintain the health percentage after `max_hp` is increased.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local player_id = EntityGetRootEntity( entity_id )
local x, y = EntityGetTransform( entity_id )

local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )
local hpdiff = 0.0
local hp = 0.0
local max_hp = 0.0

-- Iterate through VariableStorageComponents to find the 'effect_hearty' variable
if ( variablestorages ~= nil ) then
	for j,storage_id in ipairs(variablestorages) do
		local var_name = ComponentGetValue( storage_id, "name" )
		if ( var_name == "effect_hearty" ) then
			hpdiff = ComponentGetValue2( storage_id, "value_float" )
		end
	end
end

-- If 'effect_hearty' is positive, apply the health modification
if ( hpdiff > 0 ) then
	edit_component( player_id, "DamageModelComponent", function(comp,vars)
		hp = ComponentGetValue2( comp, "hp" )
		max_hp = ComponentGetValue2( comp, "max_hp" )
		
		-- Calculate current health percentage
		local diff = hp / max_hp
		
		-- Double maximum health
		max_hp = max_hp * 2.0
		-- Scale current health to maintain percentage
		hp = max_hp * diff
		
		-- Update the DamageModelComponent with new health values
		ComponentSetValue2( comp, "max_hp", max_hp )
		ComponentSetValue2( comp, "hp", hp )
	end)
end
```