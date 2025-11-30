---
title: Blood Tentacle Projectile Spawning
category: entities
---

---

# Blood Tentacle Projectile Spawning

This script defines the behavior for spawning projectiles from the Blood Tentacle boss entity in Noita.

## Key Functionality

The script iterates twice to spawn two projectiles. For each projectile:

1.  **Random Seed:** A random seed is generated based on the entity's position and the current frame number to ensure varied projectile behavior.
2.  **Arc Calculation:** A random arc (angle) between 0 and 2π radians is calculated.
3.  **Velocity Calculation:** Based on the calculated arc, horizontal (`vel_x`) and vertical (`vel_y`) velocities are determined, with a magnitude of 150.
4.  **Projectile Spawning:** The `shoot_projectile` function is called to create a projectile.
    *   **Projectile Type:** `data/entities/animals/boss_wizard/bloodtentacle.xml`
    *   **Position:** Spawned slightly above the entity's current `y` position (`y - 32`).
    *   **Velocity:** Uses the calculated `vel_x` and `vel_y`.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

for i=1,2 do
	SetRandomSeed( x * GameGetFrameNum(), y + i )
	
	local arc = Random( 0, 100 ) * 0.01 * math.pi * 2
	local vel_x = math.cos( arc ) * 150
	local vel_y = 0 - math.sin( arc ) * 150
	
	local eid = shoot_projectile( entity_id, "data/entities/animals/boss_wizard/bloodtentacle.xml", x, y - 32, vel_x, vel_y )
end
```