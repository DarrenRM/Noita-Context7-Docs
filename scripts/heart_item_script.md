---
title: Heart Item Script
category: scripts
---

# Heart Item Script

This script defines the behavior of the "Heart" item in Noita, primarily focusing on increasing the player's maximum health.

## Core Functionality

The `item_pickup` function is triggered when a player collects a Heart item. It modifies the player's `DamageModelComponent` to increase their `max_hp`.

### Key Attributes Modified

*   **`max_hp`**: The primary attribute increased by the Heart. It adds 1 to the current `max_hp`, potentially modified by a global multiplier.
*   **`max_hp_cap`**: If a `max_hp_cap` is defined for the player's `DamageModelComponent`, the `max_hp` increase is capped by this value.
*   **`max_hp_old`**: Stores the player's maximum health *before* the increase, useful for logging and potentially other game mechanics.
*   **`mLastMaxHpChangeFrame`**: Records the game frame number when the maximum HP was last changed.

### Visual and Audio Effects

*   **Particle Effects**: Spawns `heart_effect.xml` and `heart_out.xml` particle emitters at the item's location to provide visual feedback.
*   **Sound Cues**: Triggers a "item" music cue using `GameTriggerMusicCue`.
*   **Log Message**: Displays an important game message (`GamePrintImportant`) indicating the health increase, or a "blocked" message if the health increase was capped.

## Global Modifiers

*   **`HEARTS_MORE_EXTRA_HP_MULTIPLIER`**: A global variable that can be used to scale the health increase provided by each Heart. Defaults to "1".

## Code Structure

```lua
dofile( "data/scripts/game_helpers.lua" )

function item_pickup( entity_item, entity_who_picked, name )

	local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
	local variablestorages = EntityGetComponent( entity_who_picked, "VariableStorageComponent" ) -- Not directly used in this snippet

	local max_hp_old = 0
	local max_hp = 0
	local multiplier = tonumber( GlobalsGetValue( "HEARTS_MORE_EXTRA_HP_MULTIPLIER", "1" ) )
	
	local x, y = EntityGetTransform( entity_item )

	if( damagemodels ~= nil ) then
		for i,damagemodel in ipairs(damagemodels) do
			max_hp = tonumber( ComponentGetValue( damagemodel, "max_hp" ) )
			max_hp_old = max_hp
			max_hp = max_hp + 1 * multiplier -- The core health increase logic

			local max_hp_cap = tonumber( ComponentGetValue( damagemodel, "max_hp_cap" ) )
			if max_hp_cap > 0 then
				max_hp = math.min( max_hp, max_hp_cap ) -- Apply the cap
			end
			
			ComponentSetValue( damagemodel, "max_hp_old", max_hp_old )
			ComponentSetValue( damagemodel, "max_hp", max_hp )
			ComponentSetValue( damagemodel, "mLastMaxHpChangeFrame", GameGetFrameNum() )
		end
	end

	EntityLoad("data/entities/particles/image_emitters/heart_effect.xml", x, y-12)
	EntityLoad("data/entities/particles/heart_out.xml", x, y-8)
	
	-- Determine and print the log message
	local description = GameTextGet( "$logdesc_heart", tostring(math.floor(max_hp*25)) )
	if max_hp == max_hp_old then
		description =  GameTextGet( "$logdesc_heart_blocked", tostring(math.floor(max_hp*25)) )
	end

	GamePrintImportant( "$log_heart", description )
	GameTriggerMusicCue( "item" )

	-- remove the item from the game
	EntityKill( entity_item )
end
```