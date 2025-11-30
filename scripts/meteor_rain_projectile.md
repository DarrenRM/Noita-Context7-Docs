---
title: Meteor Rain Projectile
category: scripts
---

---

# Meteor Rain Projectile

This script defines the behavior for the "Meteor Rain" projectile, which spawns multiple smaller meteor projectiles.

## Key Attributes

*   **Spawns Meteors:** The primary function is to create a cluster of smaller meteor projectiles.
*   **Randomized Count:** The number of spawned meteors is randomized between 1 and 3.
*   **Randomized Direction:** Meteors are shot in various directions around the origin point.
*   **Off-Screen Origin:** Meteors are spawned at a distance (300 units) above the originating projectile.
*   **High Velocity:** Spawned meteors have a significant velocity (900 units/frame) directed downwards.
*   **Screen Shake:** Triggers a screen shake effect upon execution.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Sets a random seed based on game frame and entity position for varied results.
SetRandomSeed( GameGetFrameNum() + GetUpdatedComponentID(), pos_x + pos_y + entity_id )

-- Determines the number of meteors to spawn (1 to 3).
local count = Random(1,3)

-- Loop to spawn each meteor.
for i=1,count do
	-- Generates a random angle for the meteor's trajectory.
	local angle = math.pi * ( Random( 1, 200 ) * 0.01 )
	-- Calculates the spawn position for the meteor, offset above the origin.
	local x = pos_x + math.cos( angle ) * 300
	local y = pos_y - math.sin( angle ) * 300
	-- Calculates the velocity for the meteor, directed downwards.
	local vx = math.cos( angle + math.pi ) * 900
	local vy = 0 - math.sin( angle + math.pi ) * 900
	
	-- Shoots the 'meteor_rain_meteor.xml' projectile from the current projectile.
	shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/meteor_rain_meteor.xml", x, y, vx, vy )
end

-- Triggers a screen shake effect.
GameScreenshake( 15 )
```

## Related Entities

*   `data/entities/projectiles/deck/meteor_rain_meteor.xml`: The projectile entity that is spawned by this script.