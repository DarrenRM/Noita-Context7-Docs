---
title: Wand Generation for Daily Challenges
category: scripts
---

---

# Wand Generation for Daily Challenges

This script defines the logic for generating wands specifically for Noita's daily challenge mode. It focuses on creating unique wands by combining procedural gun generation with specific card additions.

## Core Function: `generate_daily_wand`

This function orchestrates the creation of a daily challenge wand.

### Key Parameters:

*   `cost`: The overall cost budget for the wand.
*   `level`: The difficulty level, influencing the types of spells and modifiers.
*   `force_unshuffle`: A boolean to force the wand to be unshuffleable (if true).

### Wand Generation Process:

1.  **Entity Initialization**: Gets the current entity ID and its position to set a random seed for consistent generation within a run.
2.  **Procedural Gun Combination**:
    *   Generates a series of procedural guns using `get_gun_data`.
    *   Combines these guns, prioritizing wands with `shuffle_deck_when_empty = 1` and better capacity/recharge rates. The goal is to create a more synergistic and potentially powerful wand.
3.  **Wand Construction**: Creates the actual wand entity from the combined gun data using `make_wand_from_gun_data`.
4.  **Card Addition**:
    *   **Predefined Cards**: Checks for a global variable `DAILY_WAND_CARDS_NEEDED`. If set, it splits the comma-separated string of card names and adds them to the wand, provided there's enough deck capacity. This allows for pre-designed daily wands.
    *   **Random Cards**: If no predefined cards are found, it adds random cards to the wand using `wand_add_random_cards`, influenced by the `level`.

## Helper Functions

### `mysplit`

A utility function to split a string by a given separator.

*   **Parameters**:
    *   `inputstr`: The string to split.
    *   `sep`: The separator character (defaults to whitespace).
*   **Returns**: A table of substrings.

```lua
function mysplit( inputstr, sep )
	if sep == nil then
			sep = "%s"
	end
	local t={}
	for str in string.gmatch(inputstr, "([^"..sep.."]+)") do
			table.insert(t, str)
	end
	return t
end
```

## Key Concepts for Modding

*   **Procedural Generation**: The core of this script relies on `get_gun_data` (from `gun_procedural.lua`) to create the base wand components. Understanding how `get_gun_data` works is crucial for influencing wand properties.
*   **Wand Synergy**: The logic for combining guns prioritizes certain properties like `shuffle_deck_when_empty`, `deck_capacity`, and recharge rates. Modders can tweak these priorities to influence the types of wands generated.
*   **Daily Challenge Customization**: The use of `GlobalsGetValue("DAILY_WAND_CARDS_NEEDED")` provides a direct hook for modders to define specific wands for daily challenges by setting this global variable before the wand is generated.
*   **Card Management**: The script demonstrates how to add spells (cards) to a wand, either pre-defined or randomly generated.

```lua
-- Example of how the function might be called (commented out in the source)
-- generate_daily_wand( 40, 2, false )
```