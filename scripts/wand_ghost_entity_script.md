---
title: Wand Ghost Entity Script
category: scripts
---

# Wand Ghost Entity Script

This script defines the behavior for a "wand ghost" entity in Noita. Its primary function is to pick up a specific wand and, if it fails to do so, self-destruct.

## Key Attributes and Behavior

*   **Entity Identification:**
    *   `entity_id`: Retrieves the unique identifier for the current entity.
    *   `pos_x`, `pos_y`: Gets the entity's current position.

*   **Wand Pickup Logic:**
    *   `EntityLoad("data/entities/items/wand_level_03.xml", pos_x, pos_y)`: Loads a specific wand (`wand_level_03.xml`) at the ghost's current position. This is the target item for the ghost.
    *   `ItemPickUpperComponent`: This component is essential for the entity to interact with and pick up items.
    *   `ComponentSetValue2( itempickup, "only_pick_this_entity", entity_pick_up_this_item )`: Configures the `ItemPickUpperComponent` to *only* pick up the specifically loaded wand.
    *   `GamePickUpInventoryItem( entity_ghost, entity_pick_up_this_item, false )`: Attempts to pick up the designated wand.

*   **Self-Destruction Condition:**
    *   The script checks if the entity successfully acquired the target wand.
    *   `GameGetAllInventoryItems( entity_ghost )`: Retrieves all items currently held by the ghost.
    *   If the target wand is *not* found in the ghost's inventory (`has_item == false`), the entity is immediately destroyed using `EntityKill( entity_ghost )`. This implies that a wand ghost that cannot obtain its intended wand is considered a threat.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Load the specific wand the ghost should pick up
local entity_pick_up_this_item = EntityLoad( "data/entities/items/wand_level_03.xml", pos_x, pos_y)
local entity_ghost = entity_id
local itempickup = EntityGetFirstComponent( entity_ghost, "ItemPickUpperComponent" )

if( itempickup ) then
	-- Configure the pickup component to only target the specific wand
	ComponentSetValue2( itempickup, "only_pick_this_entity", entity_pick_up_this_item )
	-- Attempt to pick up the wand
	GamePickUpInventoryItem( entity_ghost, entity_pick_up_this_item, false )
end

-- Verify if the wand was successfully picked up
local items = GameGetAllInventoryItems( entity_ghost )
local has_item = false

if( items ~= nil ) then
	for i,v in ipairs(items) do
		if( v == entity_pick_up_this_item ) then
			has_item = true
			break -- Exit loop once item is found
		end
	end
end

-- If the wand was not picked up, the ghost self-destructs
if( has_item == false ) then
	EntityKill( entity_ghost )
end
```