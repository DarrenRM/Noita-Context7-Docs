---
title: Money Drop Item (16x)
category: scripts/items
---

# Money Drop Item (16x)

This script defines a special item that drops a significant amount of money upon entity death. It inherits its core functionality from `drop_money.lua` and modifies the drop quantity.

## Key Functionality

### `death` Function

This function is called when the entity associated with this item dies.

*   **`damage_type_bit_field`**: (Number) Bitfield representing the type of damage taken.
*   **`damage_message`**: (String) A message describing the damage.
*   **`entity_thats_responsible`**: (Entity) The entity that caused the death.
*   **`drop_items`**: (Boolean) Whether items should be dropped.

This function calls `do_money_drop` with specific parameters to ensure a large money drop.

### `do_money_drop` Call

The core of this script's behavior is the call to `do_money_drop`:

```lua
do_money_drop( 16, true )
```

*   **`16`**: This argument specifies the quantity of money to drop. In this case, it's set to 16, indicating a substantial amount.
*   **`true`**: This boolean argument likely controls whether the money drop is guaranteed or has a chance to occur. Setting it to `true` suggests a guaranteed drop.

## Inheritance

This script utilizes `dofile` to include the functionality from `data/scripts/items/drop_money.lua`. This means it reuses the base logic for dropping money and only overrides or extends specific behaviors.

```lua
dofile( "data/scripts/items/drop_money.lua" )
```