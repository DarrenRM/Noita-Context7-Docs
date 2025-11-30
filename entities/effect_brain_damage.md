---
title: Effect Brain Damage
category: entities
---

# Effect Brain Damage

This entity defines a visual and gameplay effect that simulates brain damage, specifically the "DRUNK" effect in Noita.

## Key Components

### InheritTransformComponent
This component is present but empty, indicating that the entity inherits its transform properties from its parent or context.

### Base
This element inherits properties from `data/entities/particles/drunk.xml`. This is the primary source for the visual representation of the effect.

#### SpriteParticleEmitterComponent
This component, inherited from `drunk.xml`, controls the emission of particles.
*   `emission_interval_min_frames`: Minimum frames between particle emissions (20).
*   `emission_interval_max_frames`: Maximum frames between particle emissions (50).
*   `randomize_position_inside_hitbox`: Controls if particle positions are randomized within the hitbox (0, meaning no randomization).

### GameEffectComponent
This component applies a specific gameplay effect to the entity.
*   `effect`: The type of game effect applied, which is "DRUNK".
*   `frames`: The duration of the effect in game frames (1200 frames, approximately 20 seconds).