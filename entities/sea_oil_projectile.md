---
title: Sea Oil Projectile
category: entities
---

# Sea Oil Projectile

This document describes the `sea_oil.xml` entity, which defines a projectile that spawns a "sea of oil" effect.

## Key Components

### MaterialSeaSpawnerComponent

This component is responsible for spawning the oil material in a specific area.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `size.x`         | The width of the area where oil is spawned.                              |
| `size.y`         | The height of the area where oil is spawned.                             |
| `offset.x`       | Horizontal offset for the spawn area.                                    |
| `offset.y`       | Vertical offset for the spawn area.                                      |
| `speed`          | The speed at which the oil material is spawned or moves.                 |
| `noise_threshold`| Controls the density or distribution of the spawned material.            |
| `material`       | The name of the material to be spawned (in this case, "oil").            |

### LifetimeComponent

Determines how long the projectile (and its associated effects) will persist.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the projectile lasts. |

### ParticleEmitterComponent

Manages the visual particles that create the "sea of oil" effect.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The material name of the particles being emitted ("oil").                                               |
| `gravity.y`               | Vertical gravity applied to the particles. `0.0` means no vertical gravity.                             |
| `lifetime_min`            | Minimum lifetime of individual particles in frames.                                                     |
| `lifetime_max`            | Maximum lifetime of individual particles in frames.                                                     |
| `count_min`               | Minimum number of particles emitted per emission cycle.                                                 |
| `count_max`               | Maximum number of particles emitted per emission cycle.                                                 |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                                              |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                                                 |
| `airflow_force`           | The strength of airflow affecting the particles.                                                        |
| `airflow_time`            | How long the airflow effect lasts on particles.                                                         |
| `airflow_scale`           | Scales the effect of airflow.                                                                           |
| `image_animation_file`    | Path to the image animation file for the particles.                                                     |
| `image_animation_speed`   | Speed of the particle image animation.                                                                  |
| `is_emitting`             | If `1`, the particle emitter is active.                                                                 |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute      | Description                                                               |
| :------------- | :------------------------------------------------------------------------ |
| `file`         | The audio bank file containing the sound events.                          |
| `event_root`   | The root event name for the sound effect (e.g., "player_projectiles/sea_of_oil"). |
| `set_latest_event_position` | If `1`, the sound event will be positioned at the projectile's location. |