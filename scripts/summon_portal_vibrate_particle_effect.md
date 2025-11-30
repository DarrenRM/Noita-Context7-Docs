---
title: Summon Portal Vibrate Particle Effect
category: scripts/
---

# Summon Portal Vibrate Particle Effect

This script controls the visual effect of a vibrating portal, primarily by manipulating particle emitter properties and sprite scaling.

## Key Components and Functionality

### Particle Emitter Modulation

The core of the vibration effect is achieved by dynamically adjusting the `area_circle_radius` of a `ParticleEmitterComponent`.

*   **`ParticleEmitterComponent`**: This component is responsible for emitting particles.
*   **`modulate_radius`**: A specific identifier for the `ParticleEmitterComponent` targeted by this script.
*   **`area_circle_radius`**: The radius of the circular area from which particles are emitted. This value is dynamically calculated to create the pulsating/vibrating effect.

### Dynamic Scaling

The script uses trigonometric functions to create a smooth, oscillating scale for the portal's visual representation.

*   **`t = GameGetFrameNum()`**: Retrieves the current game frame number, used as a time input for the scaling calculations.
*   **`scale = math.sin(t * 0.1) * 0.75 + math.sin(t * 0.7256) * 0.25`**: This complex formula combines two sine waves with different frequencies and amplitudes to generate a non-uniform, organic-looking oscillation.
*   **`radius = map(scale, -1, 1, 5, 20)`**: Maps the calculated `scale` value (which ranges from -1 to 1) to a corresponding `radius` value between 5 and 20. This radius is then applied to the particle emitter.
*   **`scale = radius / 48`**: Further adjusts the `scale` value based on the calculated `radius`. This likely ensures the sprite scales proportionally to the particle emission area, considering a base sprite size of 48x48.

### Entity Manipulation

The script directly interacts with the entity it's attached to.

*   **`entity_id = GetUpdatedEntityID()`**: Gets the unique identifier of the entity running this script.
*   **`pos_x, pos_y = EntityGetTransform(entity_id)`**: Retrieves the current position of the entity.
*   **`EntitySetTransform(entity_id, pos_x, pos_y, 0, scale, scale)`**: Updates the entity's transform, applying the calculated `scale` to both the X and Y axes, effectively resizing the sprite.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local t = GameGetFrameNum()
local scale = math.sin(t * 0.1) * 0.75 + math.sin(t * 0.7256) * 0.25
local radius = map(scale, -1, 1, 5, 20)
scale = radius / 48 -- depends on sprite size

-- particle ring radius
local comp = EntityGetFirstComponent(entity_id, "ParticleEmitterComponent", "modulate_radius")
ComponentSetValue2(comp, "area_circle_radius", radius, radius)

-- scale sprite
EntitySetTransform(entity_id, pos_x, pos_y, 0, scale, scale)
```