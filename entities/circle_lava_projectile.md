---
title: Circle Lava Projectile
category: entities
---

# Circle Lava Projectile

This document describes the `circle_lava.xml` entity, which defines a player-created projectile that emits lava particles.

## Key Components

### ParticleEmitterComponent

This component controls the emission of lava particles.

| Attribute                 | Description                                                              |
| ------------------------- | ------------------------------------------------------------------------ |
| `emitted_material_name`   | The material of the particles to be emitted (`lava`).                    |
| `create_real_particles`   | Whether to create actual game particles (`1` for true).                  |
| `gravity.y`               | The gravitational pull on the particles (set to `0.0` for no gravity).   |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifetime of emitted particles in seconds.        |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per emission.        |
| `render_on_grid`          | Whether particles should render on the game grid (`1` for true).         |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases (`1` for true).   |
| `airflow_force`           | The force applied by airflow to the particles.                           |
| `airflow_scale`           | The scaling factor for airflow effects.                                  |
| `image_animation_file`    | The sprite sheet used for particle animation.                            |
| `set_magic_creation`      | Indicates if this is a magic-created particle (`1` for true).            |
| `is_emitting`             | Whether the emitter is currently active (`1` for true).                  |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute      | Description                                                              |
| -------------- | ------------------------------------------------------------------------ |
| `file`         | The audio bank file containing the sound events.                         |
| `event_root`   | The root event name for player projectiles, specifically `sea_of_lava`.  |
| `set_latest_event_position` | Whether to set the sound event's position to the latest emitter position (`1` for true). |

### LifetimeComponent

This component defines the total lifetime of the projectile itself.

| Attribute | Description                               |
| --------- | ----------------------------------------- |
| `lifetime`| The total lifetime of the projectile in frames (`260`). |

## Entity Attributes

| Attribute | Description                                                              |
| --------- | ------------------------------------------------------------------------ |
| `name`    | The internal name of the entity (`$projectile_default`).                 |
| `tags`    | Tags associated with the entity, including `projectile_player`.          |