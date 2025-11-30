---
title: Spore Pod Growth Projectile Behavior
category: scripts
---

---

# Spore Pod Growth Projectile Behavior

This script defines the behavior for a projectile that grows and moves away from surfaces, simulating a spore pod expanding.

## Key Attributes

*   **Movement:** The projectile moves away from the nearest surface.
*   **Surface Normal:** It utilizes the surface normal to determine the direction of outward movement.
*   **Distance to Surface:** A random distance is calculated to determine how far the projectile attempts to move from the surface.
*   **Sine Wobble:** A sinusoidal oscillation is applied to the movement vector, creating a subtle "wobble" effect.
*   **Speed:** A base speed is applied to the calculated movement vector.

## Core Logic

The script first retrieves the projectile's current position and then calculates a random `distance_to_surface`. It then attempts to find the surface normal at that location. If a surface is found, it calculates a displacement vector (`dx`, `dy`) pointing away from the surface.

A time-based sine wave is introduced to add a wobble to this displacement. Finally, the calculated and wobbled displacement is scaled by the `speed` and applied to the projectile's transform, causing it to move.

```lua
-- Retrieves the entity ID of the projectile
local entity_id = GetUpdatedEntityID()
-- Gets the current position of the projectile
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Calculates a random distance to the surface, influenced by position and entity ID
local distance_to_surface = ProceduralRandomf(pos_x, entity_id, 8, 30)
-- Defines the base speed of the projectile's movement
local speed = 0.04

-- Attempts to find the surface normal and distance to it
local found_normal,nx,ny,dist = GetSurfaceNormal( pos_x, pos_y, distance_to_surface, 12 )

-- If a surface is found:
if found_normal then
	-- Calculates the initial displacement vector away from the surface
	local dx = -nx * dist
	local dy = -ny * dist
	
	-- Adds a sine wobble to the movement
	local t = GameGetFrameNum() -- Gets the current frame number
	t = t + entity_id * 0.01 -- Adds an offset based on entity ID for unique wobbles
	local wobble = math.sin(t * 0.2) * 0.5 -- Calculates the wobble amount
	dx, dy = vec_rotate(dx, dy, wobble) -- Rotates the displacement vector by the wobble amount

	-- Scales the final displacement by the projectile's speed
	dx = dx * speed
	dy = dy * speed

	-- Updates the projectile's transform with the calculated movement
	EntitySetTransform(entity_id, pos_x + dx, pos_y + dy)
end
```