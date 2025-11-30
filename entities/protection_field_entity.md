---
title: Protection Field Entity
category: entities
---

# Protection Field Entity

This entity defines a protection field, likely used to repel certain elements or create a localized effect. It primarily utilizes Lua scripting for its behavior and Particle Emitters for visual and interactive effects.

## Key Components

### LuaComponent

This component dictates the entity's behavior through a Lua script.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script that controls the entity's logic.                    |
| `execute_every_n_frame` | How often the script's logic is executed (in frames).                       |

```xml
<LuaComponent
    script_source_file="data/scripts/buildings/protection_field.lua"
    execute_every_n_frame="50"
    >
</LuaComponent>
```

### ParticleEmitterComponent (Attracted Particles)

This component emits particles that are drawn towards the center of the field.

| Attribute                 | Description                                                                                                |
| :---------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`       | The material of the particles being emitted (e.g., "spark_yellow").                                      |
| `gravity.y`                   | The gravitational pull on the particles in the Y-axis. `0.0` means no gravity.                             |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of each emitted particle in seconds.                                      |
| `count_min`, `count_max`      | The minimum and maximum number of particles emitted per emission cycle.                                    |
| `render_on_grid`              | Whether the particles should be rendered on the game grid.                                                 |
| `fade_based_on_lifetime`      | If `1`, particles fade out as their lifetime decreases.                                                    |
| `area_circle_radius.max`      | The maximum radius of the circular area from which particles are emitted.                                  |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling how airflow affects the particles.                                                  |
| `velocity_always_away_from_center` | The force pushing particles away from the center of emission.                                              |
| `emit_cosmetic_particles`     | If `1`, these are purely visual particles.                                                                 |
| `is_emitting`                 | If `1`, the emitter is active.                                                                             |
| `draw_as_long`                | If `1`, particles are drawn as trails.                                                                     |
| `attractor_force`             | The force that pulls particles towards the center.                                                         |

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_yellow"
    gravity.y="0.0"
    lifetime_min="0.5"
    lifetime_max="1.0"
    count_min="1"
    count_max="3"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.max="96"
    cosmetic_force_create="0"
    airflow_force="0.5"
    airflow_time="0.01"
    airflow_scale="0.05"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    velocity_always_away_from_center="100"
    emit_cosmetic_particles="1"
    is_emitting="1"
    draw_as_long="1"
    attractor_force="12"
    >
</ParticleEmitterComponent>
```

### ParticleEmitterComponent (Outer Ring)

This component emits particles in a ring around the field's perimeter.

| Attribute                 | Description                                                                                                |
| :---------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`       | The material of the particles being emitted (e.g., "spark_yellow").                                      |
| `gravity.y`                   | The gravitational pull on the particles in the Y-axis. `0.0` means no gravity.                             |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifespan of each emitted particle in seconds.                                      |
| `count_min`, `count_max`      | The minimum and maximum number of particles emitted per emission cycle.                                    |
| `render_on_grid`              | Whether the particles should be rendered on the game grid.                                                 |
| `fade_based_on_lifetime`      | If `1`, particles fade out as their lifetime decreases.                                                    |
| `area_circle_radius.min`, `area_circle_radius.max` | The minimum and maximum radius of the circular area from which particles are emitted. Set to the same value for a precise ring. |
| `cosmetic_force_create`       | If `0`, particles are not created with a force.                                                            |
| `airflow_force`, `airflow_time`, `airflow_scale` | Parameters controlling how airflow affects the particles.                                                  |
| `emit_cosmetic_particles`     | If `1`, these are purely visual particles.                                                                 |
| `is_emitting`                 | If `1`, the emitter is active.                                                                             |

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_yellow"
    gravity.y="0.0"
    lifetime_min="0.2"
    lifetime_max="0.8"
    count_min="5"
    count_max="10"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.min="96"
    area_circle_radius.max="96"
    cosmetic_force_create="0"
    airflow_force="0.3"
    airflow_time="0.01"
    airflow_scale="0.05"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    emit_cosmetic_particles="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```