---
title: Starting Wand Configuration
category: scripts
---

# Starting Wand Configuration

This script defines the procedural generation logic for the player's starting wand in Noita. It randomly assigns various properties to create a unique wand each time.

## Key Wand Properties

The following attributes are randomized to create the starting wand:

*   **Name**: A random name from a predefined list.
*   **Deck Capacity**: The number of spell slots available in the wand.
*   **Actions Per Round**: How many spells can be cast in a single firing sequence.
*   **Reload Time**: The time it takes for the wand to be ready to fire again after casting.
*   **Shuffle Deck When Empty**: Whether the wand's spell order is randomized when it runs out of spells.
*   **Fire Rate Wait**: The delay between individual spell casts within a round.
*   **Spread Degrees**: The angular spread of projectiles.
*   **Speed Multiplier**: Affects the projectile speed.
*   **Mana Charge Speed**: How quickly the wand regenerates mana.
*   **Mana Max**: The maximum mana capacity of the wand.
*   **Actions**: The spells that can be added to the wand's deck.

## Procedural Generation Logic

The script utilizes helper functions to select random values from predefined ranges or lists.

### Helper Functions

*   `get_random_from(target)`: Selects and returns a single random element from a table as a string.
*   `get_multiple_random_from(target, amount_)`: Selects and returns a specified number of random elements from a table as strings.
*   `get_random_between_range(target)`: Selects and returns a random integer between the first two elements of a table (min and max).

### Wand Generation Steps

1.  **Initialization**:
    *   Retrieves the entity ID and transform of the wand.
    *   Sets a random seed based on the wand's position for consistent randomness.
    *   Gets the `AbilityComponent` of the wand.

2.  **Defining Wand Attributes**:
    *   A `gun` table is defined with potential values for various wand properties. This includes:
        *   `name`: A list of possible wand names.
        *   `deck_capacity`: A range for the number of spell slots.
        *   `actions_per_round`: Fixed at 1.
        *   `reload_time`: A range for reload duration.
        *   `shuffle_deck_when_empty`: Fixed at 0 (false).
        *   `fire_rate_wait`: A range for the delay between casts.
        *   `spread_degrees`: Fixed at 0.
        *   `speed_multiplier`: Fixed at 1.
        *   `mana_charge_speed`: A range for mana regeneration speed.
        *   `mana_max`: A range for maximum mana.
        *   `actions`: A list of possible spell actions that can be added to the wand.

3.  **Assigning Randomized Values**:
    *   Random values are selected for `mana_max` and `deck_capacity` using `get_random_between_range`.
    *   The wand's `ui_name` is set using `get_random_from`.
    *   Various `gun_config` and `gunaction_config` properties are set using `ComponentObjectSetValue` and `ComponentSetValue`, drawing random values from the defined ranges.

4.  **Adding Spells to the Deck**:
    *   The number of spells to add to the deck is determined randomly, capped by the `deck_capacity`.
    *   A random spell action is selected using `get_random_from`.
    *   A loop adds the selected spell action to the wand's deck using `AddGunAction` for the determined number of times.

```lua
-- Helper functions for random selection
function get_random_from( target )
	local rnd = Random(1, #target)
	return tostring(target[rnd])
end

function get_multiple_random_from( target, amount_ )
	local amount = amount_ or 1
	local result = {}
	for i=1,amount do
		local rnd = Random(1, #target)
		table.insert(result, tostring(target[rnd]))
	end
	return result
end

function get_random_between_range( target )
	local minval = target[1]
	local maxval = target[2]
	return Random(minval, maxval)
end

-- Get wand entity and its transform
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )
SetRandomSeed( x, y ) -- Set random seed based on position

local ability_comp = EntityGetFirstComponent( entity_id, "AbilityComponent" )

-- Define potential wand attributes
local gun = { }
gun.name = {"Bolt staff"} -- Example names, can be expanded
gun.deck_capacity = {2,3}
gun.actions_per_round = 1
gun.reload_time = {20,28}
gun.shuffle_deck_when_empty = 0 -- False
gun.fire_rate_wait = {9,15}
gun.spread_degrees = 0
gun.speed_multiplier = 1
gun.mana_charge_speed = {25,40}
gun.mana_max = {80,130}
gun.actions = {"LIGHT_BULLET","SPITTER","RUBBER_BALL","BOUNCY_ORB"} -- Example actions

-- Randomize and set wand properties
local mana_max = get_random_between_range( gun.mana_max )
local deck_capacity = get_random_between_range( gun.deck_capacity )

ComponentSetValue( ability_comp, "ui_name", get_random_from( gun.name ) )

ComponentObjectSetValue( ability_comp, "gun_config", "reload_time", get_random_between_range( gun.reload_time ) )
ComponentObjectSetValue( ability_comp, "gunaction_config", "fire_rate_wait", get_random_between_range( gun.fire_rate_wait ) )
ComponentSetValue( ability_comp, "mana_charge_speed", get_random_between_range( gun.mana_charge_speed) )

ComponentObjectSetValue( ability_comp, "gun_config", "actions_per_round", gun.actions_per_round )
ComponentObjectSetValue( ability_comp, "gun_config", "deck_capacity", deck_capacity )
ComponentObjectSetValue( ability_comp, "gun_config", "shuffle_deck_when_empty", gun.shuffle_deck_when_empty )
ComponentObjectSetValue( ability_comp, "gunaction_config", "spread_degrees", gun.spread_degrees )
ComponentObjectSetValue( ability_comp, "gunaction_config", "speed_multiplier", gun.speed_multiplier )

ComponentSetValue( ability_comp, "mana_max", mana_max )
ComponentSetValue( ability_comp, "mana", mana_max ) -- Initialize mana to max

-- Add random spells to the wand's deck
local action_count = math.min(Random(1,3), tonumber(deck_capacity)) -- Number of spells to add
local gun_action = get_random_from( gun.actions ) -- Select a random spell action

for i=1,action_count do
	AddGunAction( entity_id, gun_action ) -- Add the spell to the wand
end
```