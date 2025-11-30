---
title: Personal Laser Aim Script
category: scripts
---

---

# Personal Laser Aim Script

This script manages the behavior of the "Personal Laser" perk in Noita, specifically its aiming and emission logic. It ensures the laser correctly tracks the player's wand and emits when the wand is active.

## Key Functionality

### Wand Tracking and Laser Emission

-   **Wand Identification:** The script first identifies the wand currently held by the player.
-   **Laser Component:** It searches for a child entity with the tag "personal_laser" and retrieves its `LaserEmitterComponent`.
-   **Emission Control:**
    -   If a wand is held, the `is_emitting` property of the `LaserEmitterComponent` is set to `true`, causing the laser to fire.
    -   If no wand is held, `is_emitting` is set to `false`, deactivating the laser.

### Laser Positioning and Orientation

-   **Dynamic Offset:** The laser's position is dynamically calculated based on the wand's position, direction, and the player's current velocity. This ensures the laser stays aligned with the wand's aim.
-   **Transform Update:** The script updates the transform (position and direction) of the laser entity to match the calculated offset.

## Core Components and Attributes

### `LaserEmitterComponent`

This component is crucial for controlling the laser's visual and functional aspects.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `is_emitting`  | Boolean. Determines if the laser is currently active and firing.         |

### `VelocityComponent`

Used to retrieve the player's current velocity for more accurate laser positioning.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `mVelocity` | Table containing `x` and `y` components of the entity's velocity.        |

### `EntityTransform`

Represents the position and rotation of an entity in the game world.

| Attribute | Description                                                              |
| :-------- | :----------------------------------------------------------------------- |
| `x`, `y`  | Coordinates of the entity.                                               |
| `dir`     | Direction (angle) of the entity.                                         |

## Script Logic Breakdown

```lua
-- Initialize utility libraries
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/gun/procedural/gun_action_utils.lua")

-- Get the entity ID of the script and the player's root entity
local entity_id = GetUpdatedEntityID()
local player_id = EntityGetRootEntity( entity_id )

-- Find the wand held by the player
local wand_id = find_the_wand_held( player_id )

-- Get player's current velocity
local vx,vy = 0,0
local stuff = EntityGetFirstComponent( player_id, "VelocityComponent" )
if ( stuff ~= nil ) then
	vx,vy = ComponentGetValue2( stuff, "mVelocity" )
end

-- Find the laser entity
local c = EntityGetAllChildren( entity_id )
local laser
if ( c ~= nil ) then
	for i,v in ipairs( c ) do
		if EntityHasTag( v, "personal_laser" ) then
			laser = v
			break
		end
	end
end

-- Main logic: Control laser emission based on wand presence
if ( wand_id ~= nil ) and ( wand_id ~= NULL_ENTITY ) then
	-- Wand is held, control laser emission
	local x,y,dir = EntityGetTransform( wand_id )
	
	if ( laser ~= nil ) then
		local comp = EntityGetFirstComponentIncludingDisabled( laser, "LaserEmitterComponent" )
		
		if ( comp ~= nil ) then
			-- Enable laser emission
			ComponentSetValue2( comp, "is_emitting", true )
		end
	end
	
	-- Calculate laser's new position based on wand and player velocity
	local ox = x + math.cos( 0 - dir ) * 6 + vx * 1.5
	local oy = y - math.sin( 0 - dir ) * 6 + vy * 1.5
	
	-- Update laser's transform
	EntitySetTransform( entity_id, ox, oy + 0.5, dir )
else
	-- No wand held, disable laser emission
	if ( laser ~= nil ) then
		local comp = EntityGetFirstComponentIncludingDisabled( laser, "LaserEmitterComponent" )
		
		if ( comp ~= nil ) then
			ComponentSetValue2( comp, "is_emitting", false )
		end
	end
end
```