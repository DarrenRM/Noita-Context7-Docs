---
title: Essence Pickup Logic
category: scripts
---

# Essence Pickup Logic

This script handles the logic for when a player picks up an "essence" item in Noita. It defines how essences affect the player, their UI representation, and tracks pickup counts.

## Core Functionality

The `item_pickup` function is the main entry point for this script. It's triggered when an entity with an `ItemComponent` is picked up by another entity.

### Key Attributes & Elements

*   **`item_name`**: The internal name of the essence (e.g., "ESSENCE_FIRE").
*   **`ui_description`**: The descriptive text shown in the UI when the essence is picked up.
*   **`id`**: A unique identifier for the essence (e.g., "fire", "laser"). This is crucial for determining the specific effect.
*   **`ui_icon`**: Path to the UI icon for the essence.
*   **`sprite_icon`**: Path to the sprite used for the essence item itself.
*   **`essence_effect` Tag**: A tag added to the UI component to identify it as an essence effect.
*   **`GameAddFlagRun` / `AddFlagPersistent`**: These functions are used to mark that a specific essence has been picked up, potentially affecting game state or future events.
*   **`GlobalsGetValue` / `GlobalsSetValue`**: Used to track the number of times each essence has been picked up.
*   **`GamePrintImportant`**: Displays a message to the player indicating which essence was picked up and its description.
*   **`EntityKill`**: Removes the essence item from the game world after it's been picked up.

## Essence-Specific Effects

The script uses a series of `if/elseif` statements based on the `id` of the essence to apply specific effects.

### Example: Fire Essence

When the `id` is "fire", the following occurs:

1.  **Entity Loading**: Loads a specific entity file (`data/entities/misc/essences/fire.xml`) to apply the fire essence's effects. This entity is added as a child to the player.
2.  **Damage Resistance Buff**: Modifies the player's `DamageModelComponent` to increase resistance to "projectile" and "explosion" damage by 30% (multiplied by 1.3).

### Other Essences

The script includes placeholders for other essences like "laser", "air", "water", and "alcohol". Each of these would typically load a corresponding entity file to apply their unique effects.

```lua
function item_pickup( entity_item, entity_who_picked, item_name )
	-- fetch perk info ---------------------------------------------------

	local pos_x, pos_y = EntityGetTransform( entity_item )
	
	local essence_name = "ESSENCE_NAME_NOT_DEFINED"
	local essence_desc = "ESSENCE_DESCRIPTION_NOT_DEFINED"
	
	-- Get essence name and description from ItemComponent
	edit_component( entity_item, "ItemComponent", function(comp,vars)
		essence_name = ComponentGetValue( comp, "item_name")
		essence_desc = ComponentGetValue( comp, "ui_description")
	end)

	local id = ""
	-- Get the unique ID of the essence from VariableStorageComponent
	edit_component( entity_item, "VariableStorageComponent", function(comp,vars)
		id = ComponentGetValue( comp, "value_string" )
	end)
	
	local ui_icon = "data/ui_ui/essence_icons/" .. id .. ".png"
	local sprite_icon = "data/items_gfx/essences/" .. id .. ".png"
	
	-- Add UI icon and description component to the player
	local entity_ui = EntityCreateNew( "" )
	EntityAddComponent( entity_ui, "UIIconComponent", 
	{ 
		name = essence_name,
		description = essence_desc,
		icon_sprite_file = ui_icon
	})
	EntityAddTag( entity_ui, "essence_effect" ) -- Tag for UI identification
	EntityAddChild( entity_who_picked, entity_ui ) -- Attach UI to the player
	
	-- Apply essence-specific effects based on ID
	if (id == "fire") then
		local cid = EntityLoad( "data/entities/misc/essences/fire.xml", pos_x, pos_y )
		EntityAddChild( entity_who_picked, cid ) -- Add fire effect entity to player
		
		-- Apply damage resistance buffs for fire essence
		local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )
		if( damagemodels ~= nil ) then
			for i,damagemodel in ipairs(damagemodels) do	
				local projectile_resistance = tonumber(ComponentObjectGetValue( damagemodel, "damage_multipliers", "projectile" ))
				local explosion_resistance = tonumber(ComponentObjectGetValue( damagemodel, "damage_multipliers", "explosion" ))
				projectile_resistance = projectile_resistance * 1.3 -- Increase projectile resistance
				explosion_resistance = explosion_resistance * 1.3 -- Increase explosion resistance
				ComponentObjectSetValue( damagemodel, "damage_multipliers", "projectile", tostring(projectile_resistance) )
				ComponentObjectSetValue( damagemodel, "damage_multipliers", "explosion", tostring(explosion_resistance) )
			end
		end
		
	elseif ( id == "laser" ) then
		local cid = EntityLoad( "data/entities/misc/essences/laser.xml", pos_x, pos_y )
		EntityAddChild( entity_who_picked, cid )
	elseif ( id == "air" ) then
		local cid = EntityLoad( "data/entities/misc/essences/air.xml", pos_x, pos_y )
		EntityAddChild( entity_who_picked, cid )
	elseif ( id == "water" ) then
		local cid = EntityLoad( "data/entities/misc/essences/water.xml", pos_x, pos_y )
		EntityAddChild( entity_who_picked, cid )
	elseif ( id == "alcohol" ) then
		local cid = EntityLoad( "data/entities/misc/essences/alcohol.xml", pos_x, pos_y )
		EntityAddChild( entity_who_picked, cid )
	end
	
	-- Mark essence as picked up globally and persistently
	GameAddFlagRun( "essence_" .. id )
	AddFlagPersistent( "essence_" .. id )
	
	-- Track pickup count for this essence
	local globalskey = "ESSENCE_" .. string.upper(id) .. "_PICKUP_COUNT"
	local pickups = tonumber( GlobalsGetValue( globalskey, "0" ) )
	pickups = pickups + 1
	GlobalsSetValue( globalskey, tostring( pickups ) )

	-- cosmetic fx -------------------------------------------------------

	-- Load particle effect for visual feedback
	EntityLoad( "data/entities/particles/image_emitters/perk_effect.xml", pos_x, pos_y )
	-- Display important message to the player
	GamePrintImportant( GameTextGet( "$log_pickedup_perk", GameTextGetTranslatedOrNot( essence_name ) ), essence_desc )
	
	EntityKill( entity_item ) -- Remove the essence item from the world
end
```