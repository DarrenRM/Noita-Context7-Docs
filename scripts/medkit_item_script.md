---
title: Medkit Item Script
category: scripts
---

# Medkit Item Script

This script defines the behavior of the Medkit item in Noita. When picked up, it heals the player and then destroys itself.

## Key Functionality

### `item_pickup` Function

This function is called when the player picks up the Medkit.

*   **Heals Player:** It iterates through all `DamageModelComponent` components attached to the player entity. For each component, it increases the current `hp` by a calculated amount (0.25 * 0.6666 * 2).
*   **Clamps HP:** Ensures the healed `hp` does not exceed the `max_hp` of the player.
*   **Destroys Item:** After healing, the Medkit item entity is removed from the game using `EntityKill`.

## Important Components and Attributes

The script primarily interacts with the `DamageModelComponent` to modify player health.

### `DamageModelComponent`

This component is essential for managing health and damage.

| Attribute | Description                                                                 |
| :-------- | :-------------------------------------------------------------------------- |
| `hp`      | The current health points of the entity.                                    |
| `max_hp`  | The maximum health points the entity can have.                              |

## Code Structure

```lua
dofile( "data/scripts/game_helpers.lua" )

function item_pickup( entity_item, entity_who_picked, item_name )
	-- Get all DamageModelComponent components from the entity that picked up the item
	local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )

	if( damagemodels ~= nil ) then
		-- Iterate through each DamageModelComponent
		for i,v in ipairs(damagemodels) do
			-- Get current and maximum HP
			local hp = tonumber( ComponentGetValue( v, "hp" ) )
			local max_hp = tonumber( ComponentGetValue( v, "max_hp") )

			-- Calculate healing amount and apply it
			hp = hp + 0.25 * 0.6666 * 2
			if( hp > max_hp ) then hp = max_hp end -- Clamp HP to max_hp

			-- Set the updated HP
			ComponentSetValue( v, "hp", hp)
		end
	end

	-- Remove the medkit item from the game
	EntityKill( entity_item )
end
```