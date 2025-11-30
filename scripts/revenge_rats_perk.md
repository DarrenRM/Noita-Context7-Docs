---
title: Revenge Rats Perk
category: scripts
---

# Revenge Rats Perk

This perk spawns plague rats when the player takes damage.

## Core Functionality

The `damage_received` function is triggered when the player entity takes damage. It checks for specific conditions before spawning rats.

### Key Attributes & Logic

*   **Damage Threshold:** The perk only triggers on negative damage (healing) or if the number of existing plague rats is less than 20.
*   **Rat Spawn Count:** The number of rats spawned is determined by a global variable `RAT_PERK_TOTAL_COUNT` (representing the number of times the perk has been picked up), capped at a maximum of 10 rats per activation.
*   **Self-Damage Prevention:** The perk will not trigger if the damage was caused by the player entity itself or its parent entity.
*   **Cooldown:** A short cooldown of 2 frames is enforced between rat spawns to prevent excessive spawning.
*   **Randomization:** A random number generator is used to determine which specific rat variant to spawn (though in this implementation, only one variant `plague_rats_rat.xml` is used).

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( damage, desc, entity_who_caused, is_fatal )
	local entity_id    = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	local rats = EntityGetWithTag( "plague_rat" )
	
	-- don't revenge tentacle on heal
	if ( damage < 0 ) or ( #rats >= 20 ) then return end

	SetRandomSeed( GameGetFrameNum(), x + y + entity_id )
	local flag_name = "RAT_PERK_TOTAL_COUNT"
	local pickup_count = tonumber( GlobalsGetValue( flag_name, "0" ) )
	local rat_count = math.min( 1 + pickup_count, 10 )
	
	if ( entity_who_caused == entity_id ) or ( ( EntityGetParent( entity_id ) ~= NULL_ENTITY ) and ( entity_who_caused == EntityGetParent( entity_id ) ) ) then return end

	-- check that we're only shooting every 10 frames
	if script_wait_frames( entity_id, 2 ) then  return  end
	
	for i=1,rat_count do
		local rnd = Random( 1, 3 )
		if ( rnd == 1 ) then
			EntityLoad( "data/entities/misc/perks/plague_rats_rat.xml", x, y )
		end
	end
end
```