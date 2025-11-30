---
title: Controls F Particle Emitter
category: entities
---

# Controls F Particle Emitter

This entity defines a particle emitter that generates visual effects, specifically using an image animation. It's likely used for visual feedback or effects related to "controls F" in the game.

## Key Components

### ParticleEmitterComponent

This component handles the generation and properties of the emitted particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles being emitted (e.g., "spark").                |
| `gravity.y`               | The gravitational pull on the particles along the Y-axis.                   |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration each particle exists.                      |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                  |
| `fade_based_on_lifetime`  | If true, particles fade out as their lifetime decreases.                    |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emission events. |
| `emit_cosmetic_particles` | If true, emits particles that are purely cosmetic and don't affect gameplay. |
| `image_animation_file`    | The path to the image file used for particle animation.                     |
| `image_animation_speed`   | The speed at which the image animation plays.                               |
| `image_animation_loop`    | If true, the image animation will loop.                                     |
| `is_emitting`             | Controls whether the emitter is currently active.                           |
| `render_back`             | Whether particles should be rendered behind other game elements.            |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total duration the entity exists.     |