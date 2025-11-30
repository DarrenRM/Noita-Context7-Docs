---
title: Gray Dust Cloud Particle Emitter
category: entities
---

---

# Gray Dust Cloud Particle Emitter

This entity defines a particle effect that generates gray dust clouds. It utilizes two `SpriteParticleEmitterComponent` instances to create a layered effect with different lifetimes and emission counts.

## Key Components

### SpriteParticleEmitterComponent (Primary)

This component is responsible for the main emission of gray dust particles.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/dust_cloud_gray.xml` | Specifies the sprite used for the particles.                                |
| `lifetime`                | `60`                                | Duration each particle exists (in frames).                                  |
| `color.a`                 | `1`                                 | Initial alpha (opacity) of the particles.                                   |
| `color_change.a`          | `-1.0`                              | Rate at which the alpha changes over the particle's lifetime (fades out).   |
| `gravity.y`               | `-30`                               | Downward gravitational pull on the particles.                               |
| `emission_interval_min_frames` | `256`                               | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `256`                               | Maximum frames between particle emissions.                                  |
| `count_min`               | `5`                                 | Minimum number of particles emitted per interval.                           |
| `count_max`               | `10`                                | Maximum number of particles emitted per interval.                           |
| `randomize_velocity.min_x`| `-80`                               | Minimum random horizontal velocity applied to particles.                    |
| `randomize_velocity.max_x`| `80`                                | Maximum random horizontal velocity applied to particles.                    |
| `randomize_velocity.min_y`| `-80`                               | Minimum random vertical velocity applied to particles.                      |
| `randomize_velocity.max_y`| `80`                                | Maximum random vertical velocity applied to particles.                      |
| `randomize_position.min_x`| `-16`                               | Minimum random horizontal offset from the emitter's position.               |
| `randomize_position.max_x`| `16`                                | Maximum random horizontal offset from the emitter's position.               |
| `randomize_position.min_y`| `-16`                               | Minimum random vertical offset from the emitter's position.                 |
| `randomize_position.max_y`| `16`                                | Maximum random vertical offset from the emitter's position.                 |
| `randomize_scale.min_x`   | `-0.2`                              | Minimum random scaling applied to particles (X-axis).                       |
| `randomize_scale.max_x`   | `0.2`                               | Maximum random scaling applied to particles (X-axis).                       |
| `randomize_scale.min_y`   | `-0.2`                              | Minimum random scaling applied to particles (Y-axis).                       |
| `randomize_scale.max_y`   | `0.2`                               | Maximum random scaling applied to particles (Y-axis).                       |
| `randomize_rotation.min`  | `-0.5`                              | Minimum random rotation applied to particles.                               |
| `randomize_rotation.max`  | `0.5`                               | Maximum random rotation applied to particles.                               |
| `randomize_angular_velocity.min` | `-1.0`                             | Minimum random angular velocity applied to particles.                       |
| `randomize_angular_velocity.max` | `1.0`                              | Maximum random angular velocity applied to particles.                       |

### SpriteParticleEmitterComponent (Secondary)

This component adds a secondary layer of dust particles with a longer lifetime.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/dust_cloud_gray.xml` | Specifies the sprite used for the particles.                                |
| `lifetime`                | `200`                               | Duration each particle exists (in frames).                                  |
| `additive`                | `1`                                 | Particles are rendered additively, making them brighter.                    |
| `color.a`                 | `1`                                 | Initial alpha (opacity) of the particles.                                   |
| `color_change.a`          | `-1.0`                              | Rate at which the alpha changes over the particle's lifetime (fades out).   |
| `gravity.y`               | `-30`                               | Downward gravitational pull on the particles.                               |
| `emission_interval_min_frames` | `256`                               | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `256`                               | Maximum frames between particle emissions.                                  |
| `count_min`               | `2`                                 | Minimum number of particles emitted per interval.                           |
| `count_max`               | `5`                                 | Maximum number of particles emitted per interval.                           |
| `randomize_velocity.min_x`| `-80`                               | Minimum random horizontal velocity applied to particles.                    |
| `randomize_velocity.max_x`| `80`                                | Maximum random horizontal velocity applied to particles.                    |
| `randomize_velocity.min_y`| `-80`                               | Minimum random vertical velocity applied to particles.                      |
| `randomize_velocity.max_y`| `80`                                | Maximum random vertical velocity applied to particles.                      |
| `randomize_position.min_x`| `-16`                               | Minimum random horizontal offset from the emitter's position.               |
| `randomize_position.max_x`| `16`                                | Maximum random horizontal offset from the emitter's position.               |
| `randomize_position.min_y`| `-16`                               | Minimum random vertical offset from the emitter's position.                 |
| `randomize_position.max_y`| `16`                                | Maximum random vertical offset from the emitter's position.                 |
| `randomize_scale.min_x`   | `-0.2`                              | Minimum random scaling applied to particles (X-axis).                       |
| `randomize_scale.max_x`   | `0.2`                               | Maximum random scaling applied to particles (X-axis).                       |
| `randomize_scale.min_y`   | `-0.2`                              | Minimum random scaling applied to particles (Y-axis).                       |
| `randomize_scale.max_y`   | `0.2`                               | Maximum random scaling applied to particles (Y-axis).                       |
| `randomize_rotation.min`  | `-0.5`                              | Minimum random rotation applied to particles.                               |
| `randomize_rotation.max`  | `0.5`                               | Maximum random rotation applied to particles.                               |
| `randomize_angular_velocity.min` | `-1.0`                             | Minimum random angular velocity applied to particles.                       |
| `randomize_angular_velocity.max` | `1.0`                              | Maximum random angular velocity applied to particles.                       |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `2`   | Duration the entity exists (in seconds). |

## Notes

*   The commented-out `VelocityComponent` and `SimplePhysicsComponent` suggest that this particle effect is not intended to have physical interactions or gravity applied to the emitter itself, but rather to the individual particles.
*   The `sprite_file` pointing to `data/particles/dust_cloud_gray.xml` indicates that this entity is a particle *emitter* for a specific type of particle, rather than the particle definition itself.
*   The two `SpriteParticleEmitterComponent` instances create a more dynamic and visually interesting dust cloud by having particles with different lifespans and emission behaviors.