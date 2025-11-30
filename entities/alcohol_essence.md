---
title: Alcohol Essence
category: entities
---

# Alcohol Essence

This entity defines the "Alcohol" essence in Noita, which applies a "DRUNK" status effect to entities.

## Key Components

### `ShotEffectComponent`

This component dictates the visual trail left by projectiles affected by this essence.

*   **`extra_modifier`**: `projectile_alcohol_trail` - Specifies the visual effect applied to projectiles.

### `Base` (Particle Effect)

This section defines the particle effect associated with the Alcohol essence.

*   **`file`**: `data/entities/particles/drunk.xml` - Links to the specific particle definition for the drunk effect.
*   **`SpriteParticleEmitterComponent`**:
    *   **`emission_interval_min_frames`**: `20` - Minimum frames between particle emissions.
    *   **`emission_interval_max_frames`**: `50` - Maximum frames between particle emissions.
    *   **`randomize_position_inside_hitbox`**: `0` - Particles are emitted at fixed positions within the hitbox, not randomly.

### `GameEffectComponent`

This component applies the actual game effect to entities.

*   **`effect`**: `DRUNK` - The name of the game effect to be applied.
*   **`frames`**: `-1` - The duration of the effect. `-1` typically indicates a permanent or indefinite duration until removed by other means.