---
title: Grey Short Explosion Trail Smoke Particle
category: entities/particles
---

# Grey Short Explosion Trail Smoke Particle

This entity defines a short-lived grey smoke trail particle effect, typically used in explosions. It inherits its base properties from `base_smoke_trail.xml` and customizes its velocity and sprite emissions.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: Inherits core functionality for smoke trail particles.

### Velocity

*   **`SetStartVelocityComponent`**:
    *   `randomize_speed.min="300"`: Minimum initial speed of the particle.
    *   `randomize_speed.max="400"`: Maximum initial speed of the particle.

### Sprite Emitters

*   **`SpriteParticleEmitterComponent` (1)**:
    *   `sprite_file="data/particles/fire_blue.xml"`: Specifies the sprite file for a component of the particle trail, likely a subtle blue fire element.

*   **`SpriteParticleEmitterComponent` (2)**:
    *   `sprite_file="data/particles/smoke_cloud_tiny_grey_$[1-4].xml"`: Defines the primary sprite for the smoke trail. The `$[1-4]` indicates that one of four variations of tiny grey smoke cloud sprites will be randomly chosen.

### Material Emission

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="plasma_fading"`: Specifies that this particle emits a material named "plasma\_fading", which likely contributes to the fading effect of the smoke.