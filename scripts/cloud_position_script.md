---
title: Cloud Position Script
category: scripts
---

# Cloud Position Script

This script is designed to update the position of a projectile entity, specifically intended for cloud-like projectiles. It achieves this by raytracing downwards from the projectile's current position and applying the transform to the point where the ray hits a surface.

## Key Functionality

### Entity Identification and Transformation

*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity that this script is attached to. This is crucial for manipulating the entity's properties.
*   **`EntityApplyTransform(entity_id, x, y)`**: Updates the position of the specified entity to the new coordinates `(x, y)`.

### Surface Raytracing

*   **`RaytraceSurfaces(pos_x, pos_y, pos_x, pos_y - 40)`**: This function performs a raycast.
    *   It starts from the entity's current `pos_x`, `pos_y`.
    *   It extends downwards by 40 units (to `pos_y - 40`).
    *   It returns information about the surface hit, including the `x` and `y` coordinates of the hit point. The script specifically uses these `x` and `y` values.

## Usage Example

This script would typically be attached to a projectile entity that is meant to behave like a cloud, such as a poison cloud or a smoke cloud. When the projectile is spawned, this script ensures it settles on the ground or the nearest surface below it.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform(entity_id)
-- Raytrace downwards from the current position to find the nearest surface
local _,x,y = RaytraceSurfaces(pos_x, pos_y, pos_x, pos_y - 40)
-- Apply the transform to the entity, moving it to the hit surface
EntityApplyTransform(entity_id, x, y)
```