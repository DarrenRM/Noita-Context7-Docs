---
title: Hut Check Script
category: scripts
---

# Hut Check Script

This script handles the logic for spawning a "teleport bunker" building when specific conditions are met near the player. It checks for the presence of the player, a "normal_tablet" or "forged_tablet", and the absence of an existing "teleport_bunker".

## Key Functionality

This script's primary purpose is to act as a trigger for spawning a special building.

### Trigger Conditions

The script checks for the following conditions to be true:

*   **Player Presence:** The player unit must exist in the game world.
*   **Tablet Presence:** Either a "normal\_tablet" or a "forged\_tablet" must be found within a 32-unit radius of the script's entity.
*   **Bunker Absence:** No "teleport\_bunker" should already exist within a 32-unit radius.

### Actions Upon Trigger

If all trigger conditions are met, the script performs the following actions:

1.  **Persistent Flag:** Sets a persistent game flag.
    *   `progress_hut_a` for "normal\_tablet".
    *   `progress_hut_b` for "forged\_tablet".
2.  **Run Flag:** Sets a run-time game flag.
    *   `fishing_hut_a` for "normal\_tablet".
    *   `fishing_hut_b` for "forged\_tablet".
3.  **Particle Effect:** Spawns a `chest_effect.xml` particle emitter at the script's location.
4.  **Bunker Spawning:** Loads and spawns a new bunker entity.
    *   `teleport_bunker.xml` if a "normal\_tablet" was found.
    *   `teleport_bunker2.xml` if a "forged\_tablet" was found.
5.  **Tablet Destruction:** Destroys the tablet entity that triggered the event.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Check for player, tablets, and absence of existing bunker
local p = EntityGetWithTag( "player_unit" )
local book = EntityGetInRadiusWithTag( x, y, 32, "normal_tablet" )
local book2 = EntityGetInRadiusWithTag( x, y, 32, "forged_tablet" )
local tele = EntityGetInRadiusWithTag( x, y, 32, "teleport_bunker" )

-- Logic for normal_tablet
if ( #p > 0 ) and ( #book > 0 ) and ( #tele == 0 ) then
	for i,bk in ipairs( book ) do
		if ( EntityGetComponent( bk, "PhysicsBodyComponent" ) ~= nil ) then
			AddFlagPersistent( "progress_hut_a" )
			GameAddFlagRun( "fishing_hut_a" )
			
			EntityLoad("data/entities/particles/image_emitters/chest_effect.xml", x, y)
			EntityLoad("data/entities/buildings/teleport_bunker.xml", x, y)
			
			EntityKill( bk )
			break
		end
	end
-- Logic for forged_tablet
elseif ( #p > 0 ) and ( #book2 > 0 ) and ( #tele == 0 ) then
	for i,bk in ipairs( book2 ) do
		if ( EntityGetComponent( bk, "PhysicsBodyComponent" ) ~= nil ) then
			AddFlagPersistent( "progress_hut_b" )
			GameAddFlagRun( "fishing_hut_b" )
			
			EntityLoad("data/entities/particles/image_emitters/chest_effect.xml", x, y)
			EntityLoad("data/entities/buildings/teleport_bunker2.xml", x, y)
			
			EntityKill( bk )
			break
		end
	end
end
```