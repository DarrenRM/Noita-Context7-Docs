---
title: Procedural Gun Generation
category: scripts
---

# Procedural Gun Generation

This script defines a function `generate_gun` that procedurally generates a gun entity in Noita. It assigns random values to key gun properties, influencing its behavior and combat effectiveness.

## Core Functionality

The `generate_gun` function is designed to be called on an entity that has an `AbilityComponent`. It then modifies this component and its associated `gun_config` to create a unique gun.

```lua
function generate_gun()
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	SetRandomSeed( x, y ) -- Ensures consistent generation for a given location

	local ability_comp = EntityGetFirstComponent( entity_id, "AbilityComponent" )

	if( ability_comp ~= nil ) then
		-- ... gun generation logic ...
	end
end

generate_gun() -- Executes the generation when the script is loaded
```

## Key Gun Attributes

The script procedurally determines the following attributes for the generated gun:

### Actions Per Round

Determines how many spells can be cast in a single firing sequence before reloading.

*   **Logic:** A D10 roll determines the number of actions:
    *   1-2: 1 action
    *   3-9: 2 actions
    *   10: 3 actions

```lua
local actions = 1
local actions_D10 = D10()

if( actions_D10 >= 1 and actions_D10 <= 2 ) then actions = 1 end
if( actions_D10 >= 3 and actions_D10 <= 9 ) then actions = 2 end
if( actions_D10 == 10 ) then actions = 3 end

ComponentObjectSetValue( ability_comp, "gun_config", "actions_per_round", actions )
```

### Reload Time

The duration the gun takes to reload after its action capacity is depleted.

*   **Logic:** Base reload time of 10, plus a random value from a D10 roll multiplied by 5.

```lua
local reload = 10 + (D10() * 5)
ComponentObjectSetValue( ability_comp, "gun_config", "reload_time", reload )
```

### Shuffle Deck When Empty

Controls whether the gun's spell deck is shuffled when it runs out of spells.

*   **Logic:** By default, shuffling is enabled (`shuffle = 1`). If a D10 roll results in 10, shuffling is disabled (`shuffle = 0`).

```lua
local shuffle = 1
local shuffle_D10 = D10()

if( shuffle_D10 == 10 ) then shuffle = 0 end

ComponentObjectSetValue( ability_comp, "gun_config", "shuffle_deck_when_empty", shuffle )
```

### Deck Capacity

The maximum number of spells the gun can hold in its deck.

*   **Logic:** A D10 roll plus 4.

```lua
local capacity = D10() + 4
ComponentObjectSetValue( ability_comp, "gun_config", "deck_capacity", capacity )
```

### UI Name

The display name of the gun in the game's UI.

*   **Logic:** If a `gun_names` table is available (presumably defined elsewhere), a random name from this table is prepended to the gun's base name.

```lua
local name = ComponentGetValue( ability_comp, "ui_name" )
if( gun_names ~= nil ) then name = gun_names[ Random( 1, #gun_names ) ] .. ' ' .. name end

ComponentSetValue( ability_comp, "ui_name", name )
```

## Dependencies

*   `dofile('data/scripts/gun/procedural/gun_utilities.lua')`: This script relies on utility functions defined in `gun_utilities.lua`, which are assumed to provide functions like `D10()` for dice rolls and potentially `gun_names` for naming.