---
title: Laser Gate (Left)
category: entities
---

# Laser Gate (Left)

This document describes the `lasergate_left.xml` entity, which represents a left-facing laser gate building in Noita.

## Core Components

### SpriteComponent
This component handles the visual representation of the laser gate.

| Attribute      | Value                               | Description                                                                 |
|----------------|-------------------------------------|-----------------------------------------------------------------------------|
| `image_file`   | `data/buildings_gfx/lasergate.xml`  | Specifies the graphical asset used for the gate.                            |
| `special_scale_x` | `1`                                 | Enables special scaling along the X-axis.                                   |
| `has_special_scale` | `1`                                 | Indicates that special scaling is active.                                   |
| `offset_x`     | `0`                                 | Horizontal offset of the sprite.                                            |
| `offset_y`     | `0`                                 | Vertical offset of the sprite.                                              |

### LuaComponent
This component integrates custom Lua scripting for the gate's behavior.

| Attribute           | Value                                  | Description                                                                 |
|---------------------|----------------------------------------|-----------------------------------------------------------------------------|
| `script_source_file`| `data/scripts/buildings/lasergate_hor.lua` | The path to the Lua script that controls the gate's logic.                  |
| `execute_every_n_frame` | `10`                                   | The script will execute every 10 frames.                                    |

### LightComponent
This component adds a light source to the laser gate.

| Attribute     | Value | Description                                                                 |
|---------------|-------|-----------------------------------------------------------------------------|
| `_enabled`    | `1`   | Enables the light component.                                                |
| `radius`      | `24`  | The radius of the light emitted.                                            |
| `fade_out_time`| `1.5` | The time it takes for the light to fade out.                                |
| `r`, `g`, `b` | `230`, `120`, `230` | The RGB color values of the light (a purplish hue).                         |

### LaserEmitterComponent
This component is responsible for emitting the laser beam.

| Attribute           | Value     | Description                                                                 |
|---------------------|-----------|-----------------------------------------------------------------------------|
| `is_emitting`       | `1`       | Enables the laser emission.                                                 |
| `laser_angle_add_rad`| `3.1415`  | Adds an angle to the laser's emission direction (approximately 180 degrees). |

#### Laser Properties (Nested within `LaserEmitterComponent`)

| Attribute                   | Value   | Description                                                                 |
|-----------------------------|---------|-----------------------------------------------------------------------------|
| `damage_to_entities`        | `0.2`   | The damage dealt to entities by the laser beam.                             |
| `max_cell_durability_to_destroy` | `4`     | The maximum durability a cell can have to be destroyed by the laser.        |
| `damage_to_cells`           | `100`   | The damage dealt to terrain cells by the laser beam.                        |
| `max_length`                | `160`   | The maximum length of the laser beam.                                       |
| `beam_radius`               | `1.5`   | The radius or thickness of the laser beam.                                  |
| `hit_particle_chance`       | `10`    | The chance (in percent) of a particle effect spawning on hit.               |
| `beam_particle_chance`      | `90`    | The chance (in percent) of a particle effect spawning along the beam.       |
| `beam_particle_type`        | `plasma_fading` | The type of particle effect to spawn along the beam.                        |
| `audio_enabled`             | `0`     | Disables audio for the laser beam.                                          |

## Other Components

### SpriteAnimatorComponent
This component is present but empty, suggesting that no specific animations are defined for this entity through this component.

### CameraBoundComponent
This component likely controls how the entity interacts with the camera's view.

| Attribute   | Value     | Description                                                                 |
|-------------|-----------|-----------------------------------------------------------------------------|
| `max_count` | `30`      | Maximum number of instances that can be active within the camera's view.    |
| `distance`  | `160000`  | The distance from the camera within which the entity is considered active.  |