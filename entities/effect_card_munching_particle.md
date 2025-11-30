---
title: Effect Card Munching Particle
category: entities
---

# Effect Card Munching Particle

This entity defines a particle effect associated with "card munching" in Noita. It inherits from a base particle and applies a regeneration effect.

## Key Components

### Base Particle (`<Base file="data/entities/particles/heal.xml">`)

This indicates the entity is built upon the existing `heal.xml` particle definition, inheriting its fundamental properties.

### Sprite Particle Emitter (`<SpriteParticleEmitterComponent>`)

Controls the emission of particles.

*   **`emission_interval_min_frames`**: Minimum frames between particle emissions (10).
*   **`emission_interval_max_frames`**: Maximum frames between particle emissions (20).
*   **`randomize_position_inside_hitbox`**: Whether to randomize particle positions within the emitter's hitbox (1 - enabled).

### Game Effect (`<GameEffectComponent>`)

Applies a specific game effect to entities affected by this particle.

*   **`effect`**: The type of game effect applied ("REGENERATION").
*   **`frames`**: The duration of the effect in frames (200).