---
title: Greed Curse Pickup Logic
category: scripts
---

# Greed Curse Pickup Logic

This script defines the behavior when the "Greed Curse" item is picked up by the player. It handles the visual and gameplay effects associated with acquiring this curse.

## Core Functionality

The `item_pickup` function is the primary handler for this script. It's triggered when an entity (presumably the player) picks up the `greed_curse_pickup` item.

### Key Actions:

*   **Spawning Greed Entity:**
    *   Loads `data/entities/misc/greed_curse/greed.xml` at the pickup location. This entity likely represents the visual and functional core of the Greed Curse.
    *   Adds a `UIIconComponent` to this spawned entity, defining its in-game icon, name (`$log_curse`), and description (`$itemdesc_essence_greed`).
    *   Attaches the Greed entity as a child to the entity that picked it up, ensuring it follows the player.

*   **Spawning Associated Entities:**
    *   Loads `data/entities/buildings/teleport_start.xml` slightly below the pickup location. This might be related to the curse's mechanics or visual presentation.
    *   (Commented out) `greed_ghost_portal.xml` and `greed_crystal.xml` suggest potential other entities that could be spawned but are currently inactive.

*   **Game State Modification:**
    *   `GameAddFlagRun( "greed_curse" )`: Adds a temporary flag to the game indicating that the Greed Curse is active for the current run.
    *   `AddFlagPersistent( "greed_curse_picked" )`: Adds a persistent flag, likely to track if the player has ever picked up this curse across multiple runs.

*   **Cosmetic Effects and Feedback:**
    *   Loads `data/entities/particles/image_emitters/perk_effect.xml` to create visual particle effects at the pickup location, signifying the curse's activation.
    *   `GamePrintImportant( "$log_curse", "$logdesc_greed_curse" )`: Displays an important in-game message to the player, informing them about the Greed Curse and its description.

*   **Item Removal:**
    *   `EntityKill( entity_item )`: Removes the original pickup item from the game world after it has been processed.

### Lua Code:

```lua
dofile( "data/scripts/game_helpers.lua" )
dofile_once("data/scripts/lib/utilities.lua")

function item_pickup( entity_item, entity_who_picked, item_name )
	-- fetch perk info ---------------------------------------------------

	local pos_x, pos_y = EntityGetTransform( entity_item )
		
	local cid = EntityLoad( "data/entities/misc/greed_curse/greed.xml", pos_x, pos_y )
	EntityAddComponent( cid, "UIIconComponent", 
	{ 
		name = "$log_curse",
		description = "$itemdesc_essence_greed",
		icon_sprite_file = "data/ui_gfx/status_indicators/greed_curse.png"
	})
	EntityAddChild( entity_who_picked, cid )
	
	--EntityLoad( "data/entities/misc/greed_curse/greed_ghost_portal.xml", pos_x, pos_y - 64 )
	EntityLoad( "data/entities/buildings/teleport_start.xml", pos_x, pos_y - 66 )
	--EntityLoad( "data/entities/misc/greed_curse/greed_crystal.xml", pos_x - 48, pos_y - 24 )
	
	GameAddFlagRun( "greed_curse" )
	AddFlagPersistent( "greed_curse_picked" )

	-- cosmetic fx -------------------------------------------------------

	EntityLoad( "data/entities/particles/image_emitters/perk_effect.xml", pos_x, pos_y )
	GamePrintImportant( "$log_curse", "$logdesc_greed_curse" )
	
	EntityKill( entity_item )
end
```