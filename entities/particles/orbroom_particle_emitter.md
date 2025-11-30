---
title: Orbroom Particle Emitter
category: entities/particles
---

# Orbroom Particle Emitter

This entity defines a particle emitter that generates visual effects resembling "orbrooms" using an animated image. It's designed to be a cosmetic particle effect.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles being emitted (e.g., `spark_red`).            |
| `gravity.y`               | Vertical gravity applied to particles (0.0 means no gravity).               |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifetime of each emitted particle in seconds.       |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                     |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. Set to 0 for a single point emission. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum frames between particle emission events. |
| `emit_cosmetic_particles` | If `1`, particles are considered cosmetic and may not interact with physics. |
| `image_animation_file`    | Path to the image file used for particle animation.                         |
| `image_animation_speed`   | The speed of the image animation in frames per second.                      |
| `image_animation_loop`    | If `1`, the image animation will loop.                                      |
| `is_emitting`             | If `1`, the emitter is active.                                              |
| `render_back`             | If `1`, particles are rendered behind other game elements.                  |

### LifetimeComponent

This component defines the lifetime of the entity itself. In this case, it's disabled (`_enabled="0"`), suggesting the emitter's duration is controlled by other means or it's intended to be persistent until removed.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds. |