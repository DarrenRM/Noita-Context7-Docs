---
title: Floating Arc Projectile Behavior
category: scripts/
---

# Floating Arc Projectile Behavior

This script defines the behavior for a projectile that attempts to steer towards a specific vertical target height while maintaining horizontal momentum.

## Key Attributes

*   **`ray_distance`**: The distance the projectile will raycast downwards to find a surface or liquid.
*   **`target_y`**: The desired vertical offset from the detected surface/liquid that the projectile aims for.
*   **`max_vel_y`**: The maximum vertical velocity the projectile can achieve.

## Behavior Logic

1.  **Initialization**:
    *   Retrieves the projectile's current entity ID and position.
    *   Gets the `VelocityComponent` to manipulate its velocity.

2.  **Surface Detection**:
    *   Performs a downward `RaytraceSurfacesAndLiquiform` to detect the nearest surface or liquid within `ray_distance`.
    *   If no surface is detected, the script terminates.

3.  **Velocity Adjustment**:
    *   Calculates a new vertical velocity (`vel_y`) based on the difference between the projectile's current Y position and the detected surface's Y position, adjusted by `target_y`. This aims to pull the projectile towards the target height.
    *   Clamps the calculated `vel_y` to the `max_vel_y` to prevent excessive upward or downward acceleration.
    *   Uses `lerp` to blend the new `vel_y` with the projectile's previous vertical velocity, creating a smoother steering effect.
    *   Applies a slight friction to the horizontal velocity (`vel_x`) by multiplying it by `0.98`.

4.  **Velocity Update**:
    *   Applies the calculated `vel_x` and `vel_y` back to the projectile's `VelocityComponent`.

```lua
--[[
This script controls the movement of a projectile that attempts to steer towards a specific vertical target height.
It uses raycasting to detect surfaces and adjusts its velocity accordingly.
]]--

local ray_distance = 30
local target_y = 12
local max_vel_y = 240

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local velocity_comp = EntityGetFirstComponent( entity_id, "VelocityComponent")
if velocity_comp == nil then return end

-- Raycast downwards to find a surface or liquid
local ray_success,r_x,r_y = RaytraceSurfacesAndLiquiform( pos_x, pos_y, pos_x, pos_y + ray_distance )
if not ray_success then return end

-- Adjust velocity to steer towards the target height
local vel_x,vel_y = ComponentGetValueVector2( velocity_comp, "mVelocity")
local pvel_y = vel_y -- Store previous vertical velocity for blending

-- Calculate new vertical velocity to reach target height
vel_y = -(pos_y - r_y + target_y) * 60
vel_y = clamp(vel_y, -max_vel_y, max_vel_y) -- Apply speed limit

-- Blend new velocity with existing velocity for smoother flight
vel_y = lerp(vel_y, pvel_y, 0.5)

-- Apply slight friction to horizontal velocity
vel_x = vel_x * 0.98

-- Update the projectile's velocity
ComponentSetValueVector2( velocity_comp, "mVelocity", vel_x, vel_y)
```