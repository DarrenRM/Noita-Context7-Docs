---
title: Gold Orb Drop Behavior
category: scripts
---

# Gold Orb Drop Behavior

This script defines the behavior of the Gold Orb when it is dropped or kicked in Noita. It primarily governs the random generation of gold nuggets or other effects based on how many times the orb has been "kicked" (interacted with).

## Core Functionality

The `drop()` function is the main logic handler. It's called when the orb is dropped or kicked.

### Key Attributes & Logic

*   **`kick_count` Variable Storage:** The orb uses a `VariableStorageComponent` named `kick_count` to track how many times it has been interacted with. This count influences the drop outcome.
*   **Random Seed:** A random seed is generated using game frame number and entity position to ensure varied outcomes.
*   **Outcome Determination:** The `outcome` variable is calculated based on the `kick_count`.
    *   For the first two kicks (`count < 2`), the outcome is fixed to `10`.
    *   For kicks 3 through 4 (`count <= 4`), the outcome is at least `2`.
    *   For kicks beyond 4 (`count > 4`), the outcome is reduced by `count - 2`, with a minimum of `1`.
*   **Drop Events:** Based on the calculated `outcome`, different entities are spawned:
    *   **Outcome 1:** Spawns an `explosion.xml` and destroys the orb.
    *   **Outcome 20:** Spawns a `goldnugget_200.xml`.
    *   **Outcome 15:** Spawns two `goldnugget_50.xml` entities.
    *   **Outcome < 10:** Spawns two `goldnugget_10.xml` entities.
    *   **Default (Outcome >= 10 and not 15 or 20):** Spawns three `goldnugget_10.xml` entities.
*   **`shoot_projectile` Function:** This helper function is used to spawn the gold nugget entities at the orb's position with random velocity.

## Related Functions

*   **`kick()`:** This function simply calls the `drop()` function, meaning kicking the orb triggers the same behavior as dropping it.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function drop()
	local entity_id    = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	local comp = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "kick_count" )
	
	SetRandomSeed( GameGetFrameNum(), x + y + entity_id )
	
	if ( comp ~= nil ) then
		local count = ComponentGetValue2( comp, "value_int" )
		count = count + 1
		ComponentSetValue2( comp, "value_int", count )
		
		SetRandomSeed( x + entity_id, y - GameGetFrameNum() )
		
		local outcome = Random( 1, 22 )
		
		if ( count < 2 ) then
			outcome = 10
		elseif ( count <= 4 ) then
			outcome = math.max( outcome, 2 )
		elseif ( count > 4 ) then
			outcome = math.max( 1, outcome - ( count - 2 ) )
		end
		
		-- print( tostring( outcome ) )
		
		if ( outcome == 1 ) then
			EntityLoad( "data/entities/projectiles/deck/explosion.xml", x, y )
			EntityKill( entity_id )
			return
		elseif ( outcome == 20 ) then
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_200.xml", x, y, Random(-40,40), Random(-40,40) )
		elseif ( outcome == 15 ) then
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_50.xml", x - 8, y, Random(-40,40), Random(-40,40) )
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_50.xml", x + 8, y, Random(-40,40), Random(-40,40) )
		elseif ( outcome < 10 ) then
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x, y, Random(-40,40), Random(-40,40) )
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x, y, Random(-40,40), Random(-40,40) )
		else
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x - 8, y, Random(-40,40), Random(-40,40) )
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x + 8, y, Random(-40,40), Random(-40,40) )
			shoot_projectile( entity_id, "data/entities/items/pickup/goldnugget_10.xml", x + 8, y, Random(-40,40), Random(-40,40) )
		end
	end
end

function kick()
	drop()
end
```