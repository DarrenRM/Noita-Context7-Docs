---
title: Perk Reroll
category: scripts/perks
---

---

# Perk Reroll

This script defines the behavior for the "Perk Reroll" item in Noita. When picked up, it consumes the perk reroll item, spawns a visual particle effect, and then spawns a new perk reroll item at the same location. This effectively allows the player to reroll their available perks.

## Key Functions

### `item_pickup(entity_item, entity_who_picked, item_name)`

This function is called when a player picks up the perk reroll item.

*   **`entity_item`**: The entity representing the perk reroll item being picked up.
*   **`entity_who_picked`**: The entity of the player who picked up the item.
*   **`item_name`**: The internal name of the item (e.g., "perk_reroll").

**Behavior:**
1.  Retrieves the position of the `entity_item`.
2.  Calls `perk_reroll_perks()` (presumably a function from `perk.lua` to handle the actual perk rerolling logic).
3.  Kills the `entity_item` (the one that was picked up).
4.  Spawns a particle effect at the item's position.
5.  Spawns a new `perk_reroll.xml` entity at the item's position, making another reroll available.

```lua
function item_pickup( entity_item, entity_who_picked, item_name )
	local pos_x, pos_y = EntityGetTransform( entity_item )
	perk_reroll_perks( entity_item )
	-- spawn a new one
	EntityKill( entity_item )
	EntityLoad( "data/entities/particles/perk_reroll.xml", pos_x, pos_y )
	EntityLoad( "data/entities/items/pickup/perk_reroll.xml", pos_x, pos_y )
end
```