---
title: Money Drop Item (8x Multiplier)
category: scripts/items
---

# Money Drop Item (8x Multiplier)

This script defines an item that, when dropped (typically upon player death), triggers a money drop with an 8x multiplier. It inherits functionality from `drop_money.lua`.

## Key Functionality

### `death` Function

This function is called when the entity associated with this item dies.

*   **`damage_type_bit_field`**: (Number) Bitfield representing the type of damage taken.
*   **`damage_message`**: (String) A descriptive message about the damage.
*   **`entity_thats_responsible`**: (Entity) The entity that caused the death.
*   **`drop_items`**: (Boolean) Whether items should be dropped.

This function calls `do_money_drop` with specific parameters to ensure an 8x money drop.

### `do_money_drop` Call

The core logic for dropping money is handled by the inherited `do_money_drop` function.

*   **`8`**: This argument likely specifies the base amount or multiplier for the money drop. In this context, it's interpreted as the multiplier.
*   **`true`**: This boolean argument likely controls whether the drop is a "guaranteed" or "special" drop, or perhaps enables a specific drop behavior.

```lua
dofile( "data/scripts/items/drop_money.lua" )


function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	do_money_drop( 8, true )
end
```