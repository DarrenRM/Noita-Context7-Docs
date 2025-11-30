---
title: Glue Explosion Particle
category: entities/particles
---

# Glue Explosion Particle

This entity defines a particle effect that simulates a glue explosion. It primarily uses a sprite for visual representation and can optionally emit glue particles.

## Key Components

### SpriteComponent
This component defines the visual appearance of the explosion particle.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `image_file`              | Path to the sprite image file.                                           |
| `kill_entity_after_finished` | If set to `1`, the entity is removed after the sprite animation finishes. |
| `additive`                | Controls additive blending (0 for no, 1 for yes).                        |
| `emissive`                | Controls emissive properties (0 for no, 1 for yes).                      |

### ParticleEmitterComponent (Commented Out)
This component, when uncommented, defines the emission of smaller glue particles.

| Attribute                 | Description