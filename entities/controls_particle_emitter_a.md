---
title: Controls Particle Emitter A
category: entities
---

# Controls Particle Emitter A

This entity defines a particle emitter that uses an image animation to generate particles. It's designed for visual effects, likely related to UI or control elements within the game.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Controls whether the emitter is active (set to `0` here, likely for testing). |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark").                |
| `gravity.y`               | The gravitational pull on the particles along the Y-axis.                   |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles in seconds.        |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | If true, particles fade out as their lifetime decreases.                    |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular emission area. Set to `0` for a single point. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emission events. |
| `emit_cosmetic_particles` | Whether to emit particles that are purely cosmetic (no gameplay effect).    |
| `image_animation_file`    | The path to the image file used for animating the particle appearance.      |
| `image_animation_speed`   | The speed at which the image animation plays.                               |
| `image_animation_loop`    | Whether the image animation should loop.                                    |
| `is_emitting`             | A flag to control if the emitter is currently active.                       |
| `render_back`             | Whether to render particles behind other game elements.                     |

### LifetimeComponent

This component defines the overall lifespan of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime` | The total lifespan of the entity in seconds. |