---
title: Controls Back Particle Emitter
category: entities/particles
---

# Controls Back Particle Emitter

This entity defines a particle emitter that generates visual effects, specifically for the "controls back" element in Noita. It utilizes an image animation to create dynamic particle behavior.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Controls whether the emitter is active (set to `0` here, likely for testing or specific game states). |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark").                |
| `gravity.y`               | The gravitational pull on the particles along the Y-axis.                   |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of individual particles in seconds.        |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission cycle.     |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | If `1`, particles will fade out as their lifetime decreases.                |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. Set to `0` for a single point emission. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum frames between particle emission events. |
| `emit_cosmetic_particles` | If `1`, emits particles that are purely cosmetic and do not interact physically. |
| `image_animation_file`    | The path to the image file used for animating the particles.                |
| `image_animation_speed`   | The speed at which the image animation plays.                               |
| `image_animation_loop`    | If `1`, the image animation will loop continuously.                         |
| `is_emitting`             | If `1`, the emitter is actively producing particles.                        |
| `render_back`             | If `1`, the particles are rendered behind other game elements.              |

### LifetimeComponent

This component defines the overall lifespan of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `_enabled`| Controls whether the lifetime is active.  |
| `lifetime`| The total duration the entity exists in seconds. |