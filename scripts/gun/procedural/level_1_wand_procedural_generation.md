---
title: Level 1 Wand Procedural Generation
category: scripts/gun/procedural
---

# Level 1 Wand Procedural Generation

This script defines the procedural generation logic for a "Level 1 Wand" in Noita. It dynamically assigns spells to the wand based on a series of random checks and a calculated "total" value derived from the wand's base stats.

## Core Functionality

The `do_level1` function is the primary logic for generating the wand's spell set. It takes a `level` argument (though it's not explicitly used within the function's current implementation) and modifies the wand's `AbilityComponent`.

### Key Attributes Modified

The script primarily influences the spells added to the wand's deck. It also has a conditional check to increase `mana_max` for specific powerful spells.

*   **Spell Selection:** The core of the script is the selection of spells from predefined lists based on random chance.
*   **Card Count:** Determines how many of the selected spell(s) are added to the wand's deck.
*   **Mana Cap Adjustment:** For certain high-cost spells like "BLACK\_HOLE", the wand's `mana_max` is conditionally increased if it's below a certain threshold.

## Spell Generation Logic

The script uses a nested, probabilistic approach to determine which spells are available and how many are added.

### Base Spell Pool

The initial set of spells considered for a Level 1 Wand includes:

*   `LIGHT_BULLET`
*   `RUBBER_BALL`
*   `ARROW`
*   `DISC_BULLET`
*   `BOUNCY_ORB`
*   `BULLET`
*   `AIR_BULLET`
*   `SLIMEBALL`

### Probabilistic Spell Additions

The following spells can be added to the pool with decreasing probabilities:

1.  **BUBBLESHOT:** Added with an 85% chance.
2.  **SPITTER:** Added with a 70% chance *if* `BUBBLESHOT` was added.
3.  **LIGHT\_BULLET\_TRIGGER:** Added with a 40% chance *if* `SPITTER` was added. If added, `card_count` is set to 1.
4.  **DISC\_BULLET\_BIG:** Added with a 20% chance *if* `LIGHT_BULLET_TRIGGER` was added. If added, `card_count` is set to 1.
5.  **TENTACLE\_PORTAL:** Added with a 10% chance *if* `DISC_BULLET_BIG` was added. If added, `card_count` is set to 1. `mana_max` is set to at least 140 if it's lower.
6.  **BLACK\_HOLE\_BIG:** Added with a 10% chance *if* `TENTACLE_PORTAL` was added. If added, `card_count` is set to 1. `mana_max` is set to at least 240 if it's lower.

### "Total" Value Influence

A `total` value is calculated from `reload_time`, `fire_rate_wait`, and `spread_degrees`, with a random offset. If this `total` exceeds 50, a different set of spells is considered:

*   **Explosive Spell Pool:**
    *   `GRENADE`
    *   `BOMB`
    *   `ROCKET`
*   **Probabilistic Explosive Additions:**
    *   `DYNAMITE`: 75% chance.
    *   `FIREBALL`: 50% chance *if* `DYNAMITE` was added.
    *   `ACIDSHOT`: 40% chance *if* `FIREBALL` was added.
    *   `GLITTER_BOMB`: 30% chance *if* `ACIDSHOT` was added.
    *   `MINE`: 30% chance *if* `GLITTER_BOMB` was added.
*   In this explosive scenario, `card_count` is always set to 1.

### Utility Spell Branch

A separate branch is triggered if `Random(0, 100)` is less than 30. This branch focuses on utility spells:

*   **Utility Spell Pool:**
    *   `CLOUD_WATER`
    *   `X_RAY`
    *   `FREEZE_FIELD`
    *   `BLACK_HOLE`
    *   `TORCH`
    *   `SHIELD_FIELD`
*   **Probabilistic Utility Additions:**
    *   `ELECTROCUTION_FIELD`: 75% chance.
    *   `DIGGER`: 50% chance *if* `ELECTROCUTION_FIELD` was added.
    *   `TORCH_ELECTRIC`: 50% chance *if* `DIGGER` was added.
    *   `POWERDIGGER`: 50% chance *if* `TORCH_ELECTRIC` was added.
    *   `SOILBALL`: 50% chance *if* `POWERDIGGER` was added.
    *   `LUMINOUS_DRILL`: 50% chance *if* `SOILBALL` was added.
    *   `CHAINSAW`: 50% chance *if* `LUMINOUS_DRILL` was added.
*   In this utility scenario, `card_count` is always set to 1.

## Final Spell Assignment

After the probabilistic additions, the `card_count` is capped by the wand's `deck_capacity`. A single `card` is then randomly selected from the final `level_1_cards` pool. This card is then added to the wand's actions `card_count` times using `AddGunAction`.

A special check ensures that if "BLACK\_HOLE" is selected and `mana_max` is less than 180, `mana_max` is increased to 180.

```lua
dofile_once("data/scripts/gun/procedural/gun_procedural.lua")


function do_level1( level )

	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	SetRandomSeed( x, y )

	local ability_comp = EntityGetFirstComponent( entity_id, "AbilityComponent" )

	if( ability_comp == nil ) then
		print_error( "Couldn't find AbilityComponent for entity, it is probably not enabled" )
	end

	local reload_time = tonumber( ComponentObjectGetValue( ability_comp, "gun_config", "reload_time"  ) )
	local fire_rate_wait = tonumber( ComponentObjectGetValue( ability_comp, "gunaction_config", "fire_rate_wait" ) )
	local spread_degrees = tonumber( ComponentObjectGetValue( ability_comp, "gunaction_config", "spread_degrees" ) )
	local deck_capacity = tonumber( ComponentObjectGetValue( ability_comp, "gun_config", "deck_capacity" ) )
	local mana_max = tonumber( ComponentGetValue( ability_comp, "mana_max" ) )

	local total = reload_time + fire_rate_wait + spread_degrees
	-- print(total)
	-- print( reload_time + fire_rate_wait + spread_degrees )
	--[[
	ComponentObjectSetValue( ability_comp, "gun_config", "actions_per_round", gun["actions_per_round"] )
	ComponentObjectSetValue( ability_comp, "gun_config", "deck_capacity", gun["deck_capacity"] )
	ComponentObjectSetValue( ability_comp, "gun_config", "shuffle_deck_when_empty", gun["shuffle_deck_when_empty"] )
	ComponentObjectSetValue( ability_comp, "gunaction_config", "spread_degrees", gun["spread_degrees"] )
	ComponentObjectSetValue( ability_comp, "gunaction_config", "speed_multiplier", gun["speed_multiplier"] )
	]]--

	total = total + Random( -10, 20 )

	local level_1_cards =
	{
		"LIGHT_BULLET",
		"RUBBER_BALL",
		"ARROW",
		"DISC_BULLET",
		"BOUNCY_ORB",
		"BULLET",
		"AIR_BULLET",
		"SLIMEBALL",
	}	

	local card_count = Random( 1, 5 ) 

	-- 0.5
	if( Random( 1, 100 ) <= 85 ) then
		table.insert(level_1_cards, "BUBBLESHOT")
		
		-- 0.25
		if( Random( 1, 100 ) <= 70 ) then
			table.insert(level_1_cards, "SPITTER")
	
			-- 0.125
			if( Random( 1, 100 ) <= 40 ) then
				table.insert(level_1_cards, "LIGHT_BULLET_TRIGGER")
				card_count = 1

				-- 0.0625
				if( Random( 1, 100 ) <= 20 ) then
					table.insert(level_1_cards, "DISC_BULLET_BIG" )
					card_count = 1
					
					-- 0.00625
					if( Random( 1, 100 ) <= 10 ) then
						table.insert(level_1_cards, "TENTACLE_PORTAL" )
						card_count = 1
						if( mana_max < 140 ) then mana_max = 140 end

						-- 0.000625
						if( Random( 1, 100 ) <= 10 ) then
							table.insert(level_1_cards, "BLACK_HOLE_BIG" )
							card_count = 1
							if( mana_max < 240 ) then mana_max = 240 end
						end
					end
				end
			end
		end
	end

	if( total > 50 ) then
		level_1_cards = 
		{
			"GRENADE",
			"BOMB",
			"ROCKET"
		}
		
		if( Random( 1, 100 ) <= 75 ) then
			table.insert(level_1_cards, "DYNAMITE")
			if( Random( 1, 100 ) <= 50 ) then
				table.insert(level_1_cards, "FIREBALL")
				if( Random( 1, 100 ) <= 40 ) then
					table.insert(level_1_cards, "ACIDSHOT")
					if( Random( 1, 100 ) <= 30 ) then
						table.insert(level_1_cards, "GLITTER_BOMB")
						if( Random( 1, 100 ) <= 30 ) then
							table.insert(level_1_cards, "MINE")
						end
					end
				end
			end
		end
		card_count = 1
	end

	local do_util = Random( 0, 100 )
	if( do_util < 30 ) then
		level_1_cards = 
		{
			"CLOUD_WATER",
			"X_RAY",
			"FREEZE_FIELD",
			"BLACK_HOLE",
			"TORCH",
			"SHIELD_FIELD",
		}
		if( Random( 1, 100 ) <= 75 ) then
			table.insert(level_1_cards, "ELECTROCUTION_FIELD")
			if( Random( 1, 100 ) <= 50 ) then
				table.insert(level_1_cards, "DIGGER")

				if( Random( 1, 100 ) <= 50 ) then
					table.insert(level_1_cards, "TORCH_ELECTRIC")

					if( Random( 1, 100 ) <= 50 ) then
						table.insert(level_1_cards, "POWERDIGGER")

						if( Random( 1, 100 ) <= 50 ) then
							table.insert(level_1_cards, "SOILBALL")

							if( Random( 1, 100 ) <= 50 ) then
								table.insert(level_1_cards, "LUMINOUS_DRILL")

								if( Random( 1, 100 ) <= 50 ) then
									table.insert(level_1_cards, "CHAINSAW")
								end
							end
						end
					end
				end
			end
		end

		card_count = 1
	end


	if( card_count > deck_capacity ) then card_count = deck_capacity end

	local card = RandomFromArray( level_1_cards )
	if( card == "BLACK_HOLE" and mana_max < 180 ) then
		mana_max = 180
	end

	for i=1,card_count do
		AddGunAction( entity_id, card )
	end

end

do_level1( 1 )
```