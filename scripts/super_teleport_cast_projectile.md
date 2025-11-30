---
title: Super Teleport Cast Projectile
category: scripts
---

---

# Super Teleport Cast Projectile

This script defines the behavior for a projectile that teleports the caster to a new location.

## Core Functionality

The primary function of this script is to:

1.  **Determine Caster's Velocity:** It retrieves the current velocity of the entity casting the projectile.
2.  **Calculate Teleport Destination:** Based on the caster's velocity and a fixed offset (120 units), it calculates a target teleportation point.
3.  **Raytrace for Platforms:** It performs a raytrace to find the nearest platform in the calculated direction.
4.  **Teleport Caster:** The caster is then moved to the determined destination (either the raytraced platform or the calculated offset if no platform is found).

## Key Attributes and Logic

*   **`entity_id`**: The unique identifier for the entity performing the teleport.
*   **`pos_x`, `pos_y`**: The current position of the entity.
*   **`vel_x`, `vel_y`**: The velocity components of the entity.
*   **`angle`**: The calculated angle based on the entity's velocity, used to determine the teleport direction.
*   **`end_x`, `end_y`**: The calculated target coordinates for the teleport.
*   **`RaytracePlatforms( pos_x, pos_y, end_x, end_y )`**: This function is crucial for finding a valid teleport location. It checks for solid surfaces in the direction of `end_x`, `end_y`.
*   **`EntitySetTransform( entity_id, ex, ey )`**: This function is used to update the position of the caster to the final teleportation coordinates (`ex`, `ey`).

## Lua Code Snippet

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local vel_x,vel_y = 0,0

-- Retrieve the entity's velocity
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity" )
end)

-- Calculate the angle based on velocity
local angle = 0 - math.atan2( vel_y, vel_x )

-- Calculate the potential teleport destination
local end_x = pos_x + math.cos(angle) * 120
local end_y = pos_y - math.sin(angle) * 120

-- Raytrace to find a platform
local success,ex,ey = RaytracePlatforms( pos_x, pos_y, end_x, end_y )

-- If no platform is found, use the calculated end point
if ( success == false ) then
	ex = end_x
	ey = end_y
end

-- Set the entity's transform to the final teleport location
EntitySetTransform( entity_id, ex, ey )
```