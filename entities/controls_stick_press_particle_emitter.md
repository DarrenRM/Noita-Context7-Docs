---
title: Controls Stick Press Particle Emitter
category: entities
---

# Controls Stick Press Particle Emitter

This entity defines a particle emitter that creates visual effects when a control stick is pressed in Noita. It's designed to be triggered by game events.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                | Controls whether the emitter is active. Set to `0` by default, meaning it's disabled until triggered. |
| `emitted_material_name`   | The material of the particles to be emitted. Here, it's set to "spark".     |
| `gravity.y`               | The gravitational pull on the particles in the Y-axis. `0.0` means no gravity. |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration (in seconds) each particle will exist.     |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission event.     |
| `render_on_grid`          | Whether the particles should be rendered on the game grid. `1` means yes.   |
| `fade_based_on_lifetime`  | If `1`, particles will fade out as their lifetime decreases.                |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. `0` means emission is from a single point. |
| `cosmetic_force_create`   | If `0`, particles are not forced to be created if the game is paused or in a state where cosmetic effects are disabled. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum frames between particle emissions. `1` means particles are emitted every frame. |
| `emit_cosmetic_particles` | If `1`, particles are considered cosmetic and can be affected by game settings. |
| `image_animation_file`    | The path to the image file used for animating the particles.                |
| `image_animation_speed`   | The speed at which the particle image animation plays.                      |
| `image_animation_loop`    | If `1`, the particle image animation will loop.                             |
| `is_emitting`             | Controls whether the emitter is actively emitting particles. `1` means it is. |
| `render_back`             | If `1`, particles will be rendered behind other game elements.              |

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `_enabled`| Controls whether the lifetime component is active. Set to `0` by default. |
| `lifetime`| The total duration (in seconds) the entity will exist. |