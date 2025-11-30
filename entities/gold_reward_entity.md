---
title: Gold Reward Entity
category: entities
---

# Gold Reward Entity

This entity defines a reward that grants gold to the player when picked up. It's often associated with boss drops or special events.

## Key Functionality

The primary function of this entity is to handle the pickup logic. When the player collects this item, it calculates the gold value, adds it to the player's wallet, and spawns visual effects.

### `item_pickup` Function

This function is triggered when the player picks up the gold reward.

*   **Gold Calculation:**
    *   Starts with a base value of 8000.
    *   Multiplies the base value by the current run's orb count (`GameGetOrbCountThisRun() + 1`).
    *   Checks for a `VariableStorageComponent` named "end_gold" to potentially override the calculated value.
*   **Player Wallet Update:**
    *   Retrieves the player's current gold from their `WalletComponent`.
    *   Adds the calculated gold value to the player's total.
    *   Updates the player's `WalletComponent` with the new gold amount.
*   **Visual Effects:**
    *   Prints an important message to the player indicating the gold received.
    *   Spawns 20 "gold\_pickup" particles around the player's position for visual feedback.
*   **Entity Cleanup:**
    *   Kills the gold reward entity after it has been picked up.

## Lua Script Breakdown

```lua
dofile( "data/scripts/lib/utilities.lua" )

function item_pickup( entity_item, entity_who_picked, name )
	-- Calculate initial gold value based on orb count
	local orbcount = GameGetOrbCountThisRun() + 1
	local value = 8000 * orbcount

	-- Check for custom gold value override
	local components = EntityGetComponent( entity_item, "VariableStorageComponent" )
	if( components ~= nil ) then
		for key,comp_id in pairs(components) do 
			local var_name = ComponentGetValue( comp_id, "name" )
			if( var_name == "end_gold") then
				local extra_value = ComponentGetValueInt( comp_id, "value_int" )
				if( extra_value ~= nil ) then
					value = extra_value -- Override with custom value
				end
			end
		end
	end

	-- Display important message to the player
	GamePrintImportant( "$log_golden_statue", GameTextGet( "$logdesc_golden_statue", tostring(value) ) )
	
	local pos_x, pos_y = EntityGetTransform( entity_item )
	
	local money = 0
	
	-- Retrieve player's current gold
	local wallet_comp = EntityGetFirstComponent( entity_who_picked, "WalletComponent" )
	if wallet_comp ~= nil then
		money = ComponentGetValue2( wallet_comp, "money")
	end

	-- Add new gold to player's total
	money = money + value
	
	-- Update player's wallet
	if wallet_comp ~= nil then
		ComponentSetValue2( wallet_comp, "money", money )
	end
	
	-- Set random seed for particle effects
	SetRandomSeed( pos_x, pos_y )

	-- Spawn gold pickup particles
	for i=1,20 do
		local x = pos_x + Random(-8, 8)
		local y = pos_y + Random(-20, 2)
		shoot_projectile( entity_item, "data/entities/particles/gold_pickup.xml", x, y, 0, 0 )
	end
	
	-- Remove the gold reward entity
	EntityKill( entity_item )
end
```