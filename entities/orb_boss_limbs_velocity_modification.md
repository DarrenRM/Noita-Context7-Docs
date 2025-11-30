---
title: Orb Boss Limbs Velocity Modification
category: entities
---

# Orb Boss Limbs Velocity Modification

This documentation describes the velocity modification applied to the Orb Boss Limbs in Noita. It focuses on how the entity's movement is altered after its initial velocity is determined.

## Key Attributes and Elements

### VelocityComponent Modification

The primary modification occurs within the `VelocityComponent` of the Orb Boss Limbs entity. This section details the logic applied to alter the entity's velocity.

#### Logic Breakdown

1.  **Get Current Velocity:** The current velocity vector (`vel_x`, `vel_y`) of the entity is retrieved.
2.  **Calculate Current Angle:** The current angle of movement is calculated using `math.atan2`.
3.  **Adjust Angle:** The calculated angle is then adjusted by subtracting it from 0 and adding `math.rad(10)`. This effectively rotates the velocity vector by 10 degrees counter-clockwise relative to its current direction.
4.  **Apply New Velocity:** A new velocity vector is calculated with a magnitude of 250 units, using the adjusted angle. This ensures the entity moves at a consistent speed in the new direction.

```lua
-- Example of the velocity modification logic
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity" )

	local angle = 0 - math.atan2(vel_y,vel_x) -- Calculate current angle and invert for rotation
	angle = angle + math.rad(10)             -- Rotate by 10 degrees counter-clockwise

	vel_x = math.cos(angle) * 250            -- Apply new X velocity
	vel_y = 0-math.sin(angle) * 250          -- Apply new Y velocity

	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y) -- Set the modified velocity
end)
```

### Entity Initialization

The script begins by retrieving the entity's ID and its current transform (position). This information is necessary to access and modify the entity's components.

```lua
local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
```