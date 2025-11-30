---
title: Megalaser Projectile Launch Logic
category: scripts
---

# Megalaser Projectile Launch Logic

This script defines the behavior for launching multiple parallel "megalaser" projectiles, creating a spread effect. It handles projectile velocity, positioning, and a slight speed variation to achieve an arrow-like shape.

## Key Attributes and Elements

### Projectile Spawning and Velocity

*   **`speed`**: Base speed of the launched projectiles.
*   **`vel_x`, `vel_y`**: Calculated velocity vector based on the entity's current direction and the `speed`.
*   **Parallel Projectile Logic**: The script enables and launches up to 5 parallel projectiles.
*   **Offset Calculation**: `offset_x`, `offset_y` are calculated perpendicular to the flight direction to determine the lateral placement of parallel beams.

### Projectile Positioning and Shaping

*   **`offset`**: Controls the lateral displacement of each parallel projectile. It starts at -2 and increments for each subsequent beam.
*   **`beam_ref`**: A `VariableStorageComponent` that holds references to the individual projectile entities to be launched.
*   **Enabling Components**: Iterates through all components of a referenced beam and enables them to ensure the projectile is active.
*   **`EntitySetTransform`**: Positions each parallel projectile based on the calculated `offset` and the entity's current transform.
*   **Speed Variation (`brake`)**: A factor applied to the velocity of side projectiles to slow them down, creating an "arrow-y" shape. This is calculated as `(1 - math.abs(offset) * 0.16)`.

### Sound Effect

*   **`GamePlaySound`**: Plays a specific sound effect (`player_projectiles/megalaser/launch`) once for the entire volley, rather than for each individual projectile, to prevent duplicates.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/gun/gun.lua")
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

-- enable and launch up to 5 parallel projectiles
local offset = -2
local beams = EntityGetComponent( entity_id, "VariableStorageComponent", "beam_ref")

if( beams ~= nil ) then
	for i=1,#beams do
		local beam = ComponentGetValue2( beams[i], "value_int")

		-- enable all components
		local temp_all_components = EntityGetAllComponents(beam)
		if( temp_all_components ~= nil ) then
			for _,comp in pairs(temp_all_components) do
				EntitySetComponentIsEnabled(beam,comp,true)
			end
		end

		-- placement
		local x = pos_x + offset_x * offset
		local y = pos_y + offset_y * offset
		EntitySetTransform(beam, x, y, rot)

		-- slow down projectiles on the side for an arrow-y shape
		local vx, vy = vel_x, vel_y
		local brake = (1 - math.abs(offset) * 0.16)
		vx = vx * brake
		vy = vy * brake

		edit_component( beams[i], "VelocityComponent", function(comp,vars)
			ComponentSetValueVector2( comp, "mVelocity", vx, vy )
		end)

		offset = offset + 1
	end
end

-- sound is played here instead of the projectiles to avoid duplicates
GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/megalaser/launch", pos_x, pos_y )
```