---
title: Boss Wizard Death Behavior
category: entities
---

# Boss Wizard Death Behavior

This document details the behavior of the Boss Wizard entity upon death, as defined in `death.lua`. It outlines the items dropped, persistent flags set, and special conditions for additional drops.

## Core Death Functionality

The `death` function is triggered when the Boss Wizard entity is destroyed. It handles the creation of items, setting of persistent flags, and conditional item drops based on the cause of death.

### Key Actions on Death:

*   **Item Creation:** Spawns several "action" entities that can trigger various effects.
*   **Book and Wandstone Drop:** Guarantees the drop of a "Mestari" book and a "wandstone".
*   **Persistent Flag Setting:**
    *   `card_unlocked_mestari`: Unlocks a specific card related to the Mestari.
    *   `miniboss_wizard`: Marks the wizard as a miniboss.
*   **Conditional Drop (Drowning in Swamp):** If the wizard dies from drowning in a "swamp" material, it will also drop a "HOMING_WAND" and set the `card_unlocked_homing_wand` flag.

### Function Breakdown:

```lua
function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )

	-- Sets a random seed based on the entity's horizontal position for deterministic randomness.
	local pw = check_parallel_pos( x )
	SetRandomSeed( pw, 30 )

	-- Defines a list of potential "action" entity types to be spawned.
	local opts = { "ADD_TRIGGER", "ADD_TIMER", "ADD_DEATH_TRIGGER", "RESET", "DUPLICATE" }

	-- Spawns 5 action entities with a slight horizontal offset.
	for i=1,5 do
		CreateItemActionEntity( opts[i], x - 8 * 4 + (i-1) * 16, y )
	end

	-- Spawns the "Mestari" book.
	EntityLoad( "data/entities/items/books/book_mestari.xml",  x - 16, y )
	-- Spawns a "wandstone".
	EntityLoad( "data/entities/items/pickup/wandstone.xml",  x + 16, y )

	-- Sets persistent flags.
	AddFlagPersistent( "card_unlocked_mestari" )
	AddFlagPersistent( "miniboss_wizard" )

	-- Checks the material the entity is in to determine if it's a special drop condition.
	local material_str = ""
	local damage_comp = EntityGetFirstComponent( entity_id, "DamageModelComponent")
	if( damage_comp ~= nil ) then
		local material = ComponentGetValue( damage_comp, "mLiquidMaterialWeAreIn" )
		if( material ~= -1 ) then
			material_str = CellFactory_GetName( material )
		end
	end

	-- Conditional drop logic.
	if( damage_message == "$damage_drowning" and material_str == "swamp" ) then
		CreateItemActionEntity( "HOMING_WAND", x + 32, y )
		AddFlagPersistent( "card_unlocked_homing_wand" )
	end
end
```