---
title: Megalaser Blue Projectile Spawner
category: scripts
---

# Megalaser Blue Projectile Spawner

This script defines the behavior for spawning multiple "megalaser_blue_beam" projectiles, creating a spread effect. It calculates the initial velocity and position for each projectile based on the spawner's orientation and applies a slight velocity modification to create an arrow-like spread.

## Key Attributes

*   **`speed`**: The base speed applied to the spawned projectiles.
*   **`offset`**: Controls the lateral displacement of spawned projectiles from the spawner's center.
*   **`brake`**: A factor used to slow down projectiles on the sides, creating a fanned-out effect.
*   **`shoot_projectile_from_projectile`**: The core function used to instantiate new projectiles.

## Spawning Logic

The script iterates seven times to spawn multiple projectiles. In each iteration:

1.  **Position Calculation**:
    *   It determines a perpendicular offset (`offset_x`, `offset_y`) to the spawner's velocity vector.
    *   This offset is then used to position the new projectile relative to the spawner's current position (`pos_x`, `pos_y`).

2.  **Velocity Modification**:
    *   The initial velocity (`vel_x`, `vel_y`) is calculated based on the spawner's velocity and the `speed` attribute.
    *   A `brake` factor is applied, which is inversely proportional to the absolute lateral `offset`. This slows down projectiles further from the center, creating a spread.

3.  **Projectile Creation**:
    *   `shoot_projectile_from_projectile` is called with the spawner's entity ID, the projectile XML path (`data/entities/projectiles/megalaser_blue_beam.xml`), the calculated position, and the modified velocity.

## Sound Effect

*   A single sound effect (`data/audio/Desktop/projectiles.bank`, `projectiles/megalaser_blue/launch`) is played once for the entire volley to prevent duplicate sounds.

```lua
dofile_once("data/scripts/lib/utilities.lua")
--dofile_once("data/scripts/gun/gun.lua")
local speed = 20

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y, rot = EntityGetTransform( entity_id )

-- velocity
local vel_x,vel_y = GameGetVelocityCompVelocity(entity_id)
vel_x, vel_y = vec_normalize(vel_x, vel_y)
if vel_x == nil then return end
vel_x = vel_x * speed
vel_y = vel_y * speed

local offset_x, offset_y = vec_normalize(vel_x, vel_y)
offset_x, offset_y = vec_rotate(offset_x, offset_y, math.pi*0.5) -- perpendicular to flight direction

-- launch projectiles in parallel
local offset = -3
for i=1,7 do
	-- placement
	local x = pos_x + offset_x * offset
	local y = pos_y + offset_y * offset

	-- slow down projectiles on the side for an arrow-y shape
	local vx, vy = vel_x, vel_y
	local brake = (1 - math.abs(offset) * 0.16)
	vx = vx * brake
	vy = vy * brake

	shoot_projectile_from_projectile(entity_id, "data/entities/projectiles/megalaser_blue_beam.xml", x, y, vx, vy)

	offset = offset + 1
end

-- sound is played here instead of the projectiles to avoid duplicates
GamePlaySound( "data/audio/Desktop/projectiles.bank", "projectiles/megalaser_blue/launch", pos_x, pos_y )
```