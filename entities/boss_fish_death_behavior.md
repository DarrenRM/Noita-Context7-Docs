---
title: Boss Fish Death Behavior
category: entities
---

# Boss Fish Death Behavior

This script defines the behavior that occurs when a "boss fish" entity dies in Noita. It handles item drops, environmental effects, and game state changes.

## Core Functionality

The `death` function is triggered upon the entity's demise.

### Key Actions

*   **Environmental Transformation:** Replaces all "water" cells with "smoke" cells in the immediate vicinity.
*   **Item Spawning:**
    *   Spawns a `heart_fullhp.xml` pickup at the boss fish's location plus an offset.
    *   Spawns a `chest_random_super.xml` pickup at the boss fish's location minus an offset.
    *   Spawns a `teleport_teleroom.xml` building at the boss fish's location.
*   **Game State Flags:**
    *   Adds a temporary run flag `miniboss_fish`.
    *   Adds a persistent flag `miniboss_fish`.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	-- Convert water to smoke in the area
	ConvertMaterialEverywhere( CellFactory_GetType( "water" ), CellFactory_GetType( "smoke" ) )
	
	-- Spawn items
	EntityLoad( "data/entities/items/pickup/heart_fullhp.xml",  x + 32, y )
	EntityLoad( "data/entities/items/pickup/chest_random_super.xml",  x - 32, y )
	
	-- Spawn a teleporter
	EntityLoad( "data/entities/buildings/teleport_teleroom.xml",  x, y )
	
	-- Set game flags
	GameAddFlagRun( "miniboss_fish" )
	AddFlagPersistent( "miniboss_fish" )
end
```