---
title: Boss Robot Death Behavior
category: entities
---

# Boss Robot Death Behavior

This document describes the behavior of the Boss Robot when it dies, as defined in `death.lua`.

## Core Functionality

The `death` function is triggered when the Boss Robot is defeated. It handles the visual and gameplay consequences of its demise.

### Key Actions

*   **Explosion Effect:** Upon death, a large explosion effect (`explosion_giga.xml`) is spawned at the robot's location.
*   **Perk Drop:** A "MAP" perk is dropped at the robot's location. This likely signifies a reward or a way to reveal more of the map.
*   **Persistent Flag:** A persistent flag named `"miniboss_robot"` is added. This flag is likely used by the game to track the defeat of this specific miniboss, potentially affecting future gameplay or world state.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/perks/perk.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	-- Spawn a large explosion effect
	EntityLoad("data/entities/projectiles/deck/explosion_giga.xml", x, y)
	
	-- Drop a MAP perk
	perk_spawn( x, y, "MAP" )
	
	-- Add a persistent flag to mark the miniboss as defeated
	AddFlagPersistent( "miniboss_robot" )
end
```