---
title: Money Drop Item (32x)
category: scripts
---

# Money Drop Item (32x)

This script defines an item that drops a significant amount of money upon entity death. It inherits functionality from `drop_money.lua` and specifically triggers a 32x money drop.

## Key Functionality

### `death` Function

This function is called when the entity associated with this item dies.

*   **`damage_type_bit_field`**: (Number) Bitfield representing the type of damage taken.
*   **`damage_message`**: (String) A message describing the damage.
*   **`entity_thats_responsible`**: (Entity) The entity that caused the death.
*   **`drop_items`**: (Boolean) Whether items should be dropped.

This function calls `do_money_drop( 32, true )` to initiate the money drop.

### `do_money_drop` Call

*   **`32`**: Specifies the multiplier for the money drop (32 times the base amount).
*   **`true`**: Indicates that the money drop should occur.

## Dependencies

*   `data/scripts/items/drop_money.lua`: This script provides the core `do_money_drop` functionality.