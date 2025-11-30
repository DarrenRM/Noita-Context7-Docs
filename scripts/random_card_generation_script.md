---
title: Random Card Generation Script
category: scripts
---

# Random Card Generation Script

This script defines a function `make_random_card` that procedurally generates a random spell card within Noita. It selects a spell from a predefined list of available actions, ensuring that any required flags for spawning are met.

## Core Functionality

The primary purpose of this script is to create a spell card entity at the player's current location.

### `make_random_card()`

This function orchestrates the process of selecting and spawning a random card.

1.  **Initialization**:
    *   Retrieves the current entity ID and its transform (position).
    *   Sets a random seed based on the entity's position to ensure varied results.
    *   Initializes variables for the selected `item` and a `valid` flag.

2.  **Random Item Selection Loop**:
    *   Enters a `while` loop that continues until a valid item is found.
    *   **Random Selection**: Picks a random index from the global `actions` table.
    *   **Item Identification**: Retrieves the `id` of the selected action and converts it to lowercase.
    *   **Flag Check**:
        *   If the selected action has a `spawn_requires_flag` defined, it checks if the player currently possesses that persistent flag using `HasFlagPersistent()`.
        *   If the flag is present, `valid` is set to `true`, exiting the loop.
        *   If the action does not require a flag, `valid` is set to `true` immediately.

3.  **Entity Creation**:
    *   If a valid `item` string was successfully determined (i.e., its length is greater than 0), it calls `CreateItemActionEntity()` to spawn the corresponding spell card at the calculated `x`, `y` coordinates.
    *   If no valid item could be found after the loop (which is unlikely with a well-populated `actions` table), it prints an error message.

## Key Data Structures and Variables

*   **`actions`**: A global table (presumably defined elsewhere in Noita's data) containing information about available spell actions. Each entry in this table is expected to have at least an `id` field.
    *   **`id`**: The unique identifier for the spell action (e.g., "fireball", "lightning").
    *   **`spawn_requires_flag`** (Optional): A string representing a persistent flag that must be active for this spell to be randomly selected.

## Example Usage (Conceptual)

While this script is designed to be called directly by the game or other scripts, a conceptual example of how it might be triggered:

```lua
-- This is a conceptual example and not part of the provided script.
-- In-game, this function would be called by an entity or game event.

-- Assume 'actions' table is populated with spell data.

-- Call the function to create a random card at the player's location.
make_random_card()
```