---
title: Grey Smoke Trail Particle
category: entities/particles
---

# Grey Smoke Trail Particle

This entity defines a grey smoke trail particle effect, typically used in explosions. It inherits its base behavior from `base_smoke_trail.xml` and customizes its visual appearance and material properties.

## Key Components

### SpriteParticleEmitterComponent

This component controls the visual sprites used for the particle effect.

*   **`sprite_file`**: Specifies the sprite files to be used.
    *   `data/particles/fire_blue.xml`: Likely contributes to a subtle blueish tint or secondary effect within the smoke.
    *   `data/particles/smoke_cloud_tiny_grey_$[1-4].xml`: This is the primary sprite for the grey smoke, using variations (`$[1-4]`) for visual diversity.

### ParticleEmitterComponent

This component defines the material properties of the emitted particles.

*   **`emitted_material_name`**: Sets the material of the particles to `plasma_fading`. This suggests the smoke particles will have properties similar to fading plasma, potentially including their lifespan and how they dissipate.

## Inheritance

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: This indicates that the entity inherits fundamental properties and behaviors from a generic smoke trail particle definition. This likely includes aspects like particle movement, lifespan, and emission patterns, which are then modified by the specific components defined in this file.