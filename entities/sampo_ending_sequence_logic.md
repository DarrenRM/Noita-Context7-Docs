---
title: Sampo Ending Sequence Logic
category: entities
---

# Sampo Ending Sequence Logic

This script handles the logic for triggering different endings and the New Game+ sequence in Noita, based on player progress, orb count, and location. It determines which ending the player receives or if they initiate a New Game+ cycle.

## Core Functionality

The script primarily checks for specific conditions to trigger game endings or the New Game+ sequence. These conditions include:

*   **Orb Count:** The number of orbs collected during the current run.
*   **Player Location:** Proximity to specific "ending spots" tagged in the game world (e.g., `ending_sampo_spot_underground`, `ending_sampo_spot_mountain`).
*   **Game State Flags:** Persistent flags that track progress through different game modes or challenges (e.g., `run_nightmare`, `greed_curse`, `essence_fire`, etc.).
*   **New Game+ Level:** The current New Game+ multiplier.

## Key Attributes and Elements

### 1. Player Progress Checks

The script evaluates various player progress metrics to decide the outcome:

*   `orb_count`: The total number of orbs collected in the current run.
*   `enemies_killed`: The number of enemies defeated.
*   `GameHasFlagRun()`: Checks for temporary run-specific flags like:
    *   `greed_curse`
    *   `greed_curse_gone`
    *   `run_nightmare`
    *   `essence_fire`, `essence_air`, `essence_water`, `essence_laser` (for the "all essences" secret).
*   `SessionNumbersGetValue("NEW_GAME_PLUS_COUNT")`: Retrieves the current New Game+ level.

### 2. Ending Location Triggers

The script identifies specific locations in the game world that act as triggers for different endings:

*   `endpoint_underground`: A tagged entity representing the underground ending location.
*   `endpoint_mountain`: A tagged entity representing the mountain top ending location.
*   The script calculates the `distance_from_mountain` and `distance` to these endpoints to determine if the player is in the correct position.

### 3. New Game+ Logic

Initiating New Game+ requires specific conditions:

*   **Orb Count Threshold:** Typically requires a minimum number of orbs (e.g., 33 or a calculated `newgame_orbs_required`).
*   **Location:** The player must be near the `ending_sampo_spot_mountain`.
*   **New Game+ Level:** The `newgame_n` variable (derived from `NEW_GAME_PLUS_COUNT`) plays a role in determining the required orb count for New Game+.
*   **Action:** If conditions are met, the player's position is adjusted, orbs are reset, and the `do_newgame_plus()` function is called.

```lua
-- Example New Game+ check
if( orb_count < 33
	and
	( ( orb_count > ORB_COUNT_IN_WORLD and newgame_orbs_required >= ORB_COUNT_IN_WORLD and orb_count >= newgame_orbs_required ) or
	 ( orb_count >= newgame_orbs_required and orb_count < ORB_COUNT_IN_WORLD ) ) ) then

	local distance_from_mountain = 1000
	if( #endpoint_mountain > 0 ) then
		local ex, ey = EntityGetTransform( endpoint_mountain[1] )
		distance_from_mountain = math.abs(x - ex) + math.abs(y - ey)
	end

	if ( distance_from_mountain < 32 ) then
		-- Trigger New Game+
		GamePlaySound( "data/audio/Desktop/event_cues.bank", "event_cues/new_game_plus/create", x, y )
		EntityKill( entity_id )
		GameClearOrbsFoundThisRun()
		-- ... player position adjustment and flag setting ...
		doing_newgame_plus = true
		do_newgame_plus()
	end
end
```

### 4. Normal Ending Logic

The script branches into different "normal" ending scenarios based on orb count and location:

*   **33+ Orbs Ending (Ending 2):** Triggered when `orb_count >= 33` and the player is near the mountain top. This leads to a "happy ending."
*   **Underground Ending (Normal Ending):** Triggered when the player is near the `ending_sampo_spot_underground`. This is the standard ending.
*   **Secret Ending (Ending 1):** Triggered when the player is near the `ending_sampo_spot_mountain` but doesn't meet the criteria for New Game+ or the 33+ orb ending. This ending can be gold-themed or radioactive, depending on the orb count.

```lua
-- Example Normal Ending Logic
if( doing_newgame_plus == false ) then
	GameAddFlagRun( "ending_game_completed" )
	GameOnCompleted()

	if( orb_count >= 33 ) then
		-- ORBS >= 33 ENDINGs
		AddFlagPersistent( "secret_amulet" )
		-- ... further checks for specific variations ...
		if ( distance_from_mountain < 32 ) then
			-- Trigger Ending 2
			EntityLoad( "data/entities/particles/image_emitters/magical_symbol_fast.xml", x, y )
			AddFlagPersistent( "progress_ending2" )
			GamePlaySound( "data/audio/Desktop/event_cues.bank", "event_cues/happy_ending/create", x, y )
			GameDoEnding2()
			EntityKill( entity_id )
		end
	elseif ( #endpoint_underground > 0 ) then
		-- NORMAL ENDING
		local endpoint_id = endpoint_underground[1]
		local ex, ey = EntityGetTransform( endpoint_id )
		local distance = math.abs(x - ex) + math.abs(y - ey)

		if (distance < 32) then
			-- Trigger Normal Ending
			EntityLoad( "data/entities/particles/image_emitters/magical_symbol_fast.xml", x, y )
			AddFlagPersistent( "progress_ending0" )
			-- ... load various ending assets and play sounds ...
			EntityKill( entity_id )
		end
	elseif ( #endpoint_mountain > 0 ) then
		-- SECRET ENDING
		local endpoint_id = endpoint_mountain[1]
		local ex, ey = EntityGetTransform( endpoint_id )
		local distance = math.abs(x - ex) + math.abs(y - ey)

		if (distance < 32) then
			-- Trigger Secret Ending
			EntityLoad( "data/entities/particles/image_emitters/magical_symbol_fast.xml", x, y )
			-- ... load Midas entities based on orb count ...
			AddFlagPersistent( "progress_ending1" )
			-- ... load ending assets and play sounds ...
			EntityKill( entity_id )
		end
	end
end
```

### 5. Persistent Flag Management

The script utilizes `AddFlagPersistent()` to mark significant progress milestones that carry over between runs, influencing future game states and unlockables.

*   `progress_newgameplusplus3`
*   `secret_greed`
*   `progress_nightmare`
*   `secret_allessences`
*   `progress_ngplus`
*   `progress_ending2`
*   `progress_ending0`
*   `progress_ending1_gold`
*   `progress_ending1_toxic`
*   `progress_ending1`

### 6. Sound and Visual Effects

Various sounds and particle effects are triggered to enhance the player's experience during ending sequences and New Game+ transitions.

*   `GamePlaySound()`: Used for specific event cues.
*   `EntityLoad()`: Used to spawn particle effects and other visual elements.

### 7. Game State Manipulation

The script directly manipulates game state through functions like:

*   `GameClearOrbsFoundThisRun()`: Resets the orb count for New Game+.
*   `GameAddFlagRun()`: Adds temporary flags for the current run.
*   `GameDoEnding2()`: Executes the logic for Ending 2.
*   `ComponentSetValue()`: Modifies component properties, such as animation states or damage model attributes.

### 8. Entity Manipulation

The script interacts with game entities:

*   `GetUpdatedEntityID()`: Gets the ID of the current entity.
*   `EntityGetTransform()`: Retrieves the position of an entity.
*   `EntityGetWithTag()`: Finds entities by their tags.
*   `EntityKill()`: Destroys an entity.
*   `EntityLoad()`: Creates a new entity.
*   `EntityAddChild()`: Makes one entity a child of another.
*   `EntityGetClosestWithTag()`: Finds the closest entity with a given tag.
*   `EntityGetFirstComponent()`: Retrieves the first component of a specific type from an entity.