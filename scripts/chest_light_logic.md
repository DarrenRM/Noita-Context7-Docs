---
title: Chest Light Logic
category: scripts
---

# Chest Light Logic

This script defines the behavior of a special chest that can be unlocked by an "alchemist key" with a specific variable. It acts as a reward mechanism, granting powerful items or a random selection of items based on whether it has been opened before.

## Key Attributes and Functionality

*   **Unlock Condition:** The chest requires an "alchemist key" with a `VariableStorageComponent` where the `name` is "music_machine" and the `value_int` is `4`.
*   **First Unlock Reward:** If unlocked for the first time (checked via `HasFlagPersistent("card_unlocked_musicbox")`), the chest grants specific powerful items: `DIVIDE_2`, `DIVIDE_3`, `DIVIDE_4`, `BURST_8`, and `BURST_X`. It also sets the persistent flag `card_unlocked_musicbox` and `secret_chest_light`.
*   **Subsequent Unlocks:** If unlocked again, it provides a random selection of 3 items from the previously mentioned powerful items.
*   **Visual and Audio Feedback:** Upon unlocking, the chest triggers a green swirly particle explosion, a water circle projectile, and plays a specific chest opening sound.
*   **Entity Management:** The script kills both the "alchemist key" and the chest entity after unlocking.

## Core Logic Breakdown

The script first checks for the presence of an "alchemist key" within a radius. If found, it inspects the key's `VariableStorageComponent` for the "music\_machine" variable.

```lua
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local keys = EntityGetInRadiusWithTag( x, y, 24, "alchemist_key" )

if ( #keys > 0 ) then
	local key_id = keys[1]
	
	local variables = EntityGetComponent( key_id, "VariableStorageComponent" )
	local status = 0
	
	if ( variables ~= nil ) then
		for i,comp in ipairs(variables) do
			local name = ComponentGetValue2( comp, "name" )
			
			if ( name == "music_machine" ) then
				status = ComponentGetValue2( comp, "value_int" )
			end
		end
	end
	
	local already_done = HasFlagPersistent( "card_unlocked_musicbox" )
	
	if ( status == 4 ) then
		-- Unlock logic here
	end
end
```

### Unlock Scenarios

**First Unlock:**

```lua
if ( status == 4 ) then
	if ( already_done == false ) then
		GamePrintImportant( "$log_alchemist_key_alt_reward", "$logdesc_alchemist_key_alt_reward" )
		EntitySetComponentsWithTagEnabled( entity_id, "chest_enable", true )
		EntitySetComponentsWithTagEnabled( entity_id, "chest_disable", false )
		CreateItemActionEntity( "DIVIDE_2", x - 48, y )
		CreateItemActionEntity( "DIVIDE_3", x - 24, y )
		CreateItemActionEntity( "DIVIDE_4", x, y )
		CreateItemActionEntity( "BURST_8", x + 24, y )
		CreateItemActionEntity( "BURST_X", x + 48, y )
		AddFlagPersistent( "card_unlocked_musicbox" )
	else
		-- Subsequent unlock logic here
	end
	
	AddFlagPersistent( "secret_chest_light" )
	
	EntityLoad( "data/entities/particles/particle_explosion/main_swirly_green.xml", x, y )
	EntityLoad( "data/entities/projectiles/circle_water.xml", x, y )
	GamePlaySound( "data/audio/Desktop/misc.bank", "misc/chest_dark_open", x, y )
	
	EntityKill( key_id )
	EntityKill( entity_id )
end
```

**Subsequent Unlocks:**

```lua
else -- already_done == true
	GamePrintImportant( "$log_alchemist_chest_opened_alt", "$logdesc_alchemist_chest_opened_alt" )
	local opts = { "DIVIDE_2", "DIVIDE_3", "DIVIDE_4", "BURST_8", "BURST_X" }
	SetRandomSeed( x, y * GameGetFrameNum() )
	
	for i=1,3 do
		local rnd = Random( 1, #opts )
		local opt = opts[rnd]
		
		CreateItemActionEntity( opt, x - 8 + (i-1) * 16, y )
	end
end
```