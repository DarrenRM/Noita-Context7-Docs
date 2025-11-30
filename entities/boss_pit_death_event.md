---
title: Boss Pit Death Event
category: entities
---

# Boss Pit Death Event

This document describes the Lua script responsible for handling the death event of the Boss Pit entity in Noita. It defines the items dropped and special effects triggered upon its defeat.

## Key Functionality

The `death` function is the core of this script. It's triggered when the Boss Pit entity is destroyed and handles the following:

### Item Drops and Effects

*   **Conditional Item Spawns:** The script checks for the persistent flag `"card_unlocked_rain"`.
    *   If the flag is **true**, it spawns both `"WORM_RAIN"` and `"METEOR_RAIN"` action entities.
    *   If the flag is **false**, it also spawns `"WORM_RAIN"` and `"METEOR_RAIN"`, and additionally spawns a `"heart_fullhp.xml"` pickup.
*   **Guaranteed Wand Drops:** Regardless of the `"card_unlocked_rain"` flag, the script always spawns two wands:
    *   `"data/entities/items/wand_unshuffle_05.xml"`
    *   `"data/entities/items/wand_level_06.xml"`

### Persistent Flag Management

*   **Unlocking Rain Cards:** The script adds the persistent flag `"card_unlocked_rain"` upon the Boss Pit's death. This likely influences future gameplay mechanics related to rain effects.
*   **Miniboss Status:** The persistent flag `"miniboss_pit"` is also added, marking the Boss Pit as a defeated miniboss.

## Script Logic Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	-- Get the unique ID of the entity that just died
	local entity_id = GetUpdatedEntityID()
	-- Get the position (x, y coordinates) of the dead entity
	local x, y = EntityGetTransform( entity_id )
	-- Check if the persistent flag "card_unlocked_rain" is currently active
	local flag_status = HasFlagPersistent( "card_unlocked_rain" )
	
	-- Determine a random seed based on the entity's x-position for varied effects
	local pw = check_parallel_pos( x )
	SetRandomSeed( pw, 120 )
	
	-- Define possible rain effects
	local opts = { "WORM_RAIN", "METEOR_RAIN" }
	-- Select a random rain effect (though both are spawned regardless in this logic)
	local rnd = Random( 1, #opts )
	
	-- Conditional spawning of rain effects and a health pickup
	if flag_status then
		-- If "card_unlocked_rain" is true, spawn both rain types
		CreateItemActionEntity( "WORM_RAIN", x - 16, y )
		CreateItemActionEntity( "METEOR_RAIN", x + 16, y )
	else
		-- If "card_unlocked_rain" is false, spawn both rain types and a full health pickup
		CreateItemActionEntity( "WORM_RAIN", x - 16, y )
		CreateItemActionEntity( "METEOR_RAIN", x + 16, y )
		EntityLoad( "data/entities/items/pickup/heart_fullhp.xml",  x, y )
	end
	
	-- Spawn guaranteed wand drops
	EntityLoad( "data/entities/items/wand_unshuffle_05.xml",  x - 24, y )
	EntityLoad( "data/entities/items/wand_level_06.xml",  x + 24, y )
	
	-- Set persistent flags to indicate progression
	AddFlagPersistent( "card_unlocked_rain" )
	AddFlagPersistent( "miniboss_pit" )
end
```