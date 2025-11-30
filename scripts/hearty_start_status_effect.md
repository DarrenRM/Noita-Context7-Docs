---
title: Hearty Start Status Effect
category: scripts
---

---

# Hearty Start Status Effect

This script defines a status effect that grants the player a significant health boost upon starting a new run. It modifies the player's maximum health and current health, ensuring they start with a substantial advantage.

## Key Attributes and Behavior

*   **Health Modification:** The primary function is to increase the player's `max_hp` by 50% and set their current `hp` to 50% of this new maximum.
*   **Conditional Application:** The effect is prevented from applying under specific conditions:
    *   If the player's initial `max_hp` is less than or equal to 0.4.
    *   If the player is a "boss\_centipede" and has collected 33 or more orbs in the current run.
*   **Variable Storage:** The effect's application and any stored health difference are managed through a `VariableStorageComponent`.
*   **Health Difference Storage:** If the effect is applied, the original `max_hp` value (before modification) is stored in the `VariableStorageComponent` under the name "effect\_hearty". This might be used for later calculations or to revert the effect.
*   **Removal:** If the conditions for applying the effect are not met, the associated `VariableStorageComponent` is removed from the entity.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local player_id = EntityGetParent( entity_id )
local x, y = EntityGetTransform( entity_id )

-- Ensure the script is running on a valid player entity
if ( player_id ~= NULL_ENTITY ) and ( entity_id ~= player_id ) then
	local variablestorages = EntityGetComponent( entity_id, "VariableStorageComponent" )
	local dcomps = EntityGetComponent( player_id, "DamageModelComponent" )
	local hpdiff = 0.0 -- Stores the original max_hp
	
	local stop = false -- Flag to prevent effect application

	if ( dcomps ~= nil ) then
		for j,comp in ipairs( dcomps ) do
			local hp = ComponentGetValue2( comp, "hp" )
			local max_hp = ComponentGetValue2( comp, "max_hp" )
			
			-- Check conditions to stop the effect
			if ( max_hp <= 0.4 ) or ( EntityHasTag( player_id, "boss_centipede" ) and ( GameGetOrbCountThisRun() >= 33 ) ) then
				stop = true
			end
			
			-- Apply the health boost if not stopped
			if ( stop == false ) then
				local diff = hp / max_hp -- Calculate current health percentage
				hpdiff = max_hp -- Store original max_hp
				
				max_hp = max_hp * 0.5 -- Increase max_hp by 50%
				hp = math.max( max_hp * diff, 0.04 ) -- Set current hp to 50% of new max, with a minimum
				
				ComponentSetValue2( comp, "max_hp", max_hp )
				ComponentSetValue2( comp, "hp", hp )
			end
		end
	end

	-- Manage the VariableStorageComponent
	if ( variablestorages ~= nil ) then
		for j,storage_id in ipairs( variablestorages ) do
			local var_name = ComponentGetValue( storage_id, "name" )
			if ( var_name == "effect_hearty" ) then
				if ( stop == false ) then
					-- Store the original max_hp if effect is applied
					ComponentSetValue2( storage_id, "value_float", hpdiff )
				else
					-- Remove the storage if effect is not applied
					EntityRemoveComponent( entity_id, storage_id )
				end
				
				break -- Exit loop once the relevant storage is found and processed
			end
		end
	end
end