---
title: Mouse Controls Image Emitter
category: entities
---

# Mouse Controls Image Emitter

This entity defines a particle emitter that displays an animated image, likely for visual feedback related to mouse controls.

## Key Components

### ParticleEmitterComponent

This component handles the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., "spark").                |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifetime of each emitted particle in seconds.       |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The interval in frames between particle emission events. |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects not affecting gameplay). |
| `image_animation_file`    | The path to the image file used for the particle animation.                 |
| `image_animation_speed`   | The speed of the image animation.                                           |
| `image_animation_loop`    | Whether the image animation should loop.                                    |
| `is_emitting`             | Whether the emitter is currently active.                                    |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`  | The total lifetime of the entity in frames. |