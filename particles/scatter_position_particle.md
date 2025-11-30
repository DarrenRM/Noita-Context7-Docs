---
title: Scatter Position Particle
category: particles
---

# Scatter Position Particle

This script modifies the position of a particle entity, scattering it away from its current velocity vector. It's designed to create a more dynamic and dispersed particle effect.

## Key Functionality

*   **Randomized Scattering:** The particle's final position is influenced by a random deviation from its current velocity.
*   **Distance Control:** The maximum distance the particle can scatter is randomized within a defined range.
*   **Camera Bounds Check:** The scattering logic only applies if the particle is within the camera's view, optimizing performance.
*   **Surface Raytracing:** The script performs a raytrace to ensure the scattered position doesn't go through solid surfaces.
*   **Trail Emission:** If the particle has a `ParticleEmitterComponent`, its emission position is updated to the new scattered location, preventing trails from the original position.

## Core Attributes & Logic

### `max_distance`

*   **Description:** Determines the maximum distance the particle can scatter from its original position.
*   **Type:** Float
*   **Range:** Randomized between 4 and 16.

### `random_rot`

*   **Description:** Controls the maximum angular deviation (in radians) from the particle's velocity vector.
*   **Type:** Float
*   **Value:** 0.4

### Velocity Calculation

1.  The script retrieves the particle's current velocity (`dx`, `dy`).
2.  The velocity vector is normalized to get its direction.
3.  The normalized velocity is multiplied by `max_distance` to get a scattering vector.

### Direction Deviation

*   The scattering vector is then rotated by a random angle between `-random_rot` and `random_rot` using `vec_rotate`. This introduces the scattering effect.

### Raytracing

*   `RaytraceSurfaces` is used to find the actual position (`x`, `y`) where the particle should land, ensuring it stops at the first surface encountered along the scattered path.

### Entity Transformation

*   `EntityApplyTransform` updates the particle's position to the calculated `x`, `y`.

### Trail Emission Update

*   If a `ParticleEmitterComponent` is present, `mExPosition` is updated to the new `x`, `y`. This ensures that any subsequent particles emitted by this emitter originate from the scattered position, not the original one.

```lua
-- Example of how the max_distance is calculated
local max_distance = ProceduralRandomf(x, entity_id, 4, 16)

-- Example of how the direction is deviated
local dx,dy = vec_rotate(dx,dy,ProceduralRandomf(entity_id, y, -random_rot, random_rot))

-- Example of updating the emitter's position
local comp = EntityGetFirstComponent(entity_id, "ParticleEmitterComponent")
if( comp ~= nil ) then
	ComponentSetValue2(comp, "mExPosition", x, y)
end
```