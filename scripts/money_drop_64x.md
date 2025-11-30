---
title: Money Drop (64x)
category: scripts
---

# Money Drop (64x)

This script defines a special money drop behavior for Noita, specifically designed to drop 64 units of gold. It inherits functionality from a base `drop_money.lua` script.

## Core Functionality

The primary purpose of this script is to trigger a money drop event when a specific condition is met.

### `death` Function

This function is called when an entity dies. It's responsible for initiating the money drop.

*   **`damage_type_bit_field`**: A bitfield representing the type of damage that caused the death.
*   **`damage_message`**: A string containing a message about the damage.
*   **`entity_thats_responsible`**: The entity that caused the death.
*   **`drop_items`**: A boolean indicating whether items should be dropped.

### `do_money_drop( amount, is_special )`

This function, inherited from `drop_money.lua`, handles the actual money drop.

*   **`amount`**: The quantity of gold to drop. In this script, it's hardcoded to `64`.
*   **`is_special`**: A boolean flag. When `true` (as in this script), it signifies a special drop, potentially affecting its appearance or behavior.

## Usage Example

This script is typically attached to an entity that, upon its death, should result in a significant gold drop. The `death` function is automatically invoked by the game engine.

```lua
dofile( "data/scripts/items/drop_money.lua" )

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	do_money_drop( 64, true ) -- Drops 64 gold as a special item
end
```