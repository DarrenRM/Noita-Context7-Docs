---
title: Boss Alchemist Death Behavior
category: entities
---

# Boss Alchemist Death Behavior

This script defines the behavior when the Boss Alchemist entity is defeated. It handles item drops, persistent flags, and visual effects.

## Core Functionality

The `death` function is triggered upon the entity's demise. It takes parameters related to the damage received and the entity responsible for the kill.

### Key Actions:

*   **Randomized Item Drops:** Spawns a selection of specific items based on a random algorithm.
*   **Persistent Flag Management:** Sets persistent flags for game progression and tracking.
*   **Special Item Spawning:** Drops a unique item related to the boss.

## Item Dropping Logic

The script determines which items to drop based on whether the "card\_unlocked\_duplicate" flag is active.

### Item Pool:

The following items are randomly selected for dropping:

*   `ALPHA`
*   `OMEGA`
*   `GAMMA`
*   `MU`
*   `ZETA`
*   `PHI`
*   `TAU`
*   `SIGMA`

### Drop Conditions:

*   **If `card_unlocked_duplicate` is TRUE:**
    *   Four unique items from the item pool are dropped.
*   **If `card_unlocked_duplicate` is FALSE:**
    *   Four unique items from the item pool are dropped.
    *   A `heart_fullhp.xml` pickup is spawned.

## Persistent Flags

Upon death, the following persistent flags are set:

*   `card_unlocked_duplicate`: This flag likely influences future item drops or game mechanics.
*   `miniboss_alchemist`: Marks the defeat of this specific miniboss.

## Entity Spawning

The script explicitly spawns the following entities upon the Boss Alchemist's death:

*   **`data/entities/animals/boss_alchemist/key.xml`**: A key item associated with the boss.
*   **`data/entities/items/pickup/heart_fullhp.xml`**: (Conditional, when `card_unlocked_duplicate` is FALSE) A full HP pickup.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	local flag_status = HasFlagPersistent( "card_unlocked_duplicate" )
	
	local pw = check_parallel_pos( x )
	SetRandomSeed( pw, 60 )
	
	local opts = { "ALPHA", "OMEGA", "GAMMA", "MU", "ZETA", "PHI", "TAU", "SIGMA" }
	local rnd = Random( 1, #opts )
	
	if flag_status then
		for i=1,4 do
			rnd = Random( 1, #opts )
			CreateItemActionEntity( opts[rnd], x - 8 * 4 + (i-1) * 16, y )
			table.remove( opts, rnd )
		end
	else
		for i=1,4 do
			rnd = Random( 1, #opts )
			CreateItemActionEntity( opts[rnd], x - 8 * 4 + (i-1) * 16, y )
			table.remove( opts, rnd )
		end
		EntityLoad( "data/entities/items/pickup/heart_fullhp.xml",  x, y )
	end
	
	EntityLoad( "data/entities/animals/boss_alchemist/key.xml",  x, y )
	
	AddFlagPersistent( "card_unlocked_duplicate" )
	AddFlagPersistent( "miniboss_alchemist" )
end
```