---
title: Image Emitter Controls B
category: entities
---

# Image Emitter Controls B

This entity defines a particle emitter that uses an image animation to control particle generation. It's designed for cosmetic effects and is likely used in conjunction with other game elements.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Controls whether the emitter is active (set to `0` here, likely for testing). |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark").                |
| `gravity.y`               | The gravitational pull on the particles in the Y-axis.                      |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles in seconds.        |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                     |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum frames between particle emission events. |
| `emit_cosmetic_particles` | If `1`, particles are considered cosmetic and may have different behaviors.  |
| `image_animation_file`    | The path to the image file used for animation.                              |
| `image_animation_speed`   | The speed at which the image animation plays.                               |
| `image_animation_loop`    | If `1`, the image animation will loop.                                      |
| `is_emitting`             | If `1`, the emitter is actively producing particles.                        |
| `render_back`             | If `1`, particles are rendered behind other game elements.                  |

### LifetimeComponent

This component defines the overall lifespan of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifespan of the entity in seconds. |