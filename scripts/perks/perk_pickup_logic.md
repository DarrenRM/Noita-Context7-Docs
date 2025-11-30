---
title: Perk Pickup Logic
category: scripts/perks
---

# Perk Pickup Logic

This script defines the core logic for how perks are picked up by the player in Noita. It handles the interaction between the perk item and the player entity, determining which perks are removed or kept.

## Key Functions

### `item_pickup( entity_item, entity_who_picked, item_name )`

This is the primary function called when a player interacts with a perk item.

*   **`entity_item`**: The entity representing the perk item being picked up.
*   **`entity_who_picked`**: The entity of the player who picked up the item.
*   **`item_name`**: The internal name of the perk item.

This function first checks for a `VariableStorageComponent` on the perk item. If found, it looks for a variable named `"perk_dont_remove_others"`. If this variable is set to `true`, it prevents the removal of other existing perks.

Finally, it calls the `perk_pickup` function (presumably from `perk.lua`) with additional parameters to manage perk removal.

## Core Logic

The main logic revolves around the `kill_other_perks` variable, which defaults to `true`. This variable dictates whether picking up the current perk should remove any previously acquired perks.

*   **`kill_other_perks = true`**: By default, picking up a new perk will remove any existing perks the player has.
*   **`kill_other_perks = false`**: If the perk item has a `VariableStorageComponent` with a boolean variable named `"perk_dont_remove_others"` set to `true`, then existing perks will not be removed.

This mechanism allows for certain perks to be "stackable" or to not interfere with existing perk selections.