---
title: Large Explosion Smoke Trail Particle
category: entities/particles
---

# Large Explosion Smoke Trail Particle

This document describes the configuration for a large smoke trail particle used in explosions within Noita. It inherits base properties from `base_smoke_trail.xml` and modifies specific components to define its behavior and appearance.

## Key Components and Attributes

### Base Entity

*   **`<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">`**: This indicates that the particle inherits its fundamental properties from a shared base configuration for smoke trails.

### Velocity Component

*   **`<VelocityComponent air_friction="8.0">`**:
    *   `air_friction`: Controls how quickly the particle loses velocity due to air resistance. A value of `8.0` suggests a moderate level of friction.

### Set Start Velocity Component

*   **`<SetStartVelocityComponent randomize_speed.min="300" randomize_speed.max="1200">`**:
    *   `randomize_speed.min`: The minimum initial speed of the particle in pixels per second.
    *   `randomize_speed.max`: The maximum initial speed of the particle in pixels per second. This range ensures variation in the particle's initial movement.

### Die If Speed Below Component

*   **`<DieIfSpeedBelowComponent min_speed="40">`**:
    *   `min_speed`: The particle will be destroyed if its speed drops below this threshold (40 pixels per second). This prevents particles from lingering indefinitely when they have lost all momentum.

### Sprite Particle Emitter Component (Velocity Randomization)

*   **`<SpriteParticleEmitterComponent randomize_velocity.min_y="-20" randomize_velocity.max_y="10" randomize_velocity.min_x="-10" randomize_velocity.max_x="10">`**:
    *   This component applies a random offset to the particle's velocity upon emission.
    *   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Controls the vertical velocity variation.
    *   `randomize_velocity.min_x`, `randomize_velocity.max_x`: Controls the horizontal velocity variation. This adds a slight chaotic spread to the smoke trail.

### Sprite Particle Emitter Component (Sprite Definition)

*   **`<SpriteParticleEmitterComponent sprite_file="data/particles/smoke_cloud_$[1-4].xml" render_back="1">`**:
    *   `sprite_file`: Specifies the sprite to be used for this particle. The `$[1-4]` indicates that one of four different smoke cloud sprites will be randomly chosen, adding visual variety.
    *   `render_back`: When set to `1`, this particle will be rendered behind other elements, ensuring it doesn't obscure foreground objects.