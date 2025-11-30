---
title: Wand Good 3 - Procedural Generation
category: entities
---

# Wand Good 3 - Procedural Generation

This document describes the procedural generation logic for `wand_good_3.lua`, a type of wand in Noita. This wand is designed to have randomized stats and a selection of powerful spells.

## Key Attributes

This wand is characterized by its randomized stats, aiming for a balance between power and usability.

### Core Wand Properties

*   **`name`**: A table of possible names for the wand. The generated wand will randomly select one from this list.
    *   Example: `{"Scattershot wand"}`
*   **`deck_capacity`**: The maximum number of spells the wand can hold in its deck.
    *   Value: `26`
*   **`actions_per_round`**: The number of spells that can be cast per wand action.
    *   Value: `26`
*   **`reload_time`**: A range for the time it takes to reload the wand.
    *   Example: `{24, 38}` (randomly chosen between 24 and 38 frames)
*   **`shuffle_deck_when_empty`**: Determines if the deck is shuffled when empty.
    *   Value: `0` (false)
*   **`fire_rate_wait`**: A range for the delay between consecutive spell casts.
    *   Example: `{5, 10}` (randomly chosen between 5 and 10 frames)
*   **`spread_degrees`**: A range for the angular spread of projectiles.
    *   Example: `{3, 8}` (randomly chosen between 3 and 8 degrees)
*   **`speed_multiplier`**: A multiplier applied to projectile speed.
    *   Value: `1.5`
*   **`mana_charge_speed`**: A range for the speed at which mana regenerates.
    *   Example: `{300, 500}` (randomly chosen between 300 and 500)
*   **`mana_max`**: A range for the maximum mana capacity of the wand.
    *   Example: `{1200, 1500}` (randomly chosen between 1200 and 1500)

### Spell Pool

*   **`actions`**: A list of powerful spells that can be randomly assigned to the wand.
    *   Examples: `"GRENADE_TIER_3"`, `"ROCKET_TIER_3"`, `"METEOR"`, `"HEAVY_BULLET"`, `"DISC_BULLET"`

## Generation Logic

The script uses utility functions to randomize wand properties and assign spells.

### Key Functions Used

*   **`get_random_from(target)`**: Selects a single random element from a table.
*   **`get_random_between_range(target)`**: Selects a random integer within a specified range (min, max).
*   **`EntityGetTransform(entity_id)`**: Retrieves the position of the entity.
*   **`SetRandomSeed(x, y + GameGetFrameNum())`**: Initializes the random number generator based on entity position and game frame for consistent randomness.
*   **`EntityGetFirstComponent(entity_id, "AbilityComponent")`**: Retrieves the `AbilityComponent` for modifying wand properties.
*   **`ComponentSetValue(ability_comp, "ui_name", ...)`**: Sets the user interface name of the wand.
*   **`ComponentObjectSetValue(ability_comp, "gun_config", ...)`**: Sets specific properties within the `gun_config` table of the `AbilityComponent`.
*   **`ComponentObjectSetValue(ability_comp, "gunaction_config", ...)`**: Sets specific properties within the `gunaction_config` table of the `AbilityComponent`.
*   **`AddGunAction(entity_id, gun_action)`**: Adds a spell action to the wand's deck.

### Spell Assignment

The wand is generated with a fixed number of spell slots (`action_count = 8`). For each slot, a random spell is chosen from the `gun.actions` list and added to the wand.

```lua
local action_count = 8
local gun_action = get_random_from( gun.actions )

for i=1,action_count do
	--AddGunActionPermanent( entity_id, gun_action ) -- Commented out, likely for testing or alternative behavior
	AddGunAction( entity_id, gun_action )
end
```