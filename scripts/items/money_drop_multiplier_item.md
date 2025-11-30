---
title: Money Drop Multiplier Item
category: scripts/items
---

# Money Drop Multiplier Item

This script defines an item that, when picked up, modifies the money drop behavior of enemies. Specifically, it causes enemies to drop twice the amount of money.

## Functionality

The core logic is handled by the `death` function, which is called when the entity holding this item dies.

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This function overrides the default death behavior for the entity.

*   **`do_money_drop( 2, true )`**: This is the key function call.
    *   The first argument, `2`, indicates a multiplier of 2x for the money drop.
    *   The second argument, `true`, likely signifies that this is a special drop event.

## Dependencies

*   `dofile( "data/scripts/items/drop_money.lua" )`: This line ensures that the necessary `do_money_drop` function from the base money drop script is available.

## Usage

This script is intended to be attached to an item entity. When a player collects this item, its `death` function will be triggered upon the player's death, applying the 2x money drop bonus.