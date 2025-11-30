---
title: Explosion Trail Smoke Particle
category: entities/particles
---

# Explosion Trail Smoke Particle

This entity defines a smoke particle effect used in explosions, specifically for creating a trailing smoke visual. It inherits its base functionality from `base_smoke_trail.xml` and customizes the sprite used for the smoke.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: This indicates that the entity inherits all properties and behaviors from the `base_smoke_trail.xml` file. This is the foundation for the smoke trail's behavior.

### SpriteParticleEmitterComponent

This component is responsible for emitting particles.

*   **`sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml"`**: This is the crucial attribute that defines the visual appearance of the smoke particles. It specifies a sprite file that uses a numbered sequence (`$[1-4]`) to randomly select one of four different tiny smoke cloud sprites for each emitted particle. This adds variation to the smoke trail.