---
title: Laser Gate (Down) Entity
category: entities
---

# Laser Gate (Down) Entity

This document describes the `lasergate_down.xml` entity, which represents a downward-facing laser gate in Noita. This entity is primarily used for decorative purposes and environmental effects, as its laser does not deal significant damage to entities.

## Key Components

### SpriteComponent
This component defines the visual appearance of the laser gate.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `image_file`  | Path to the sprite image file.                  |
| `special_scale_x` | Controls horizontal scaling of the sprite.    |
| `has_special_scale` | Enables special scaling effects.              |
| `offset_x`    | Horizontal offset for the sprite.               |
| `offset_y`    | Vertical offset for the sprite.                 |

### LuaComponent
This component links the entity to a Lua script for custom behavior.

| Attribute          | Description                                       |
|--------------------|---------------------------------------------------|
| `script_source_file` | Path to the Lua script file.                      |
| `execute_every_n_frame` | How often the script's logic is executed.     |

### LightComponent
This component adds a light source to the entity, contributing to the visual atmosphere.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `_enabled`     | Whether the light component is active.          |
| `radius`       | The radius of the light's influence.            |
| `fade_out_time`| How long it takes for the light to fade out.    |
| `r`, `g`, `b`  | RGB values defining the light's color.          |

### LaserEmitterComponent
This component enables the entity to emit a laser beam.

#### Laser Properties
The nested `<laser>` tag defines the characteristics of the emitted laser beam.

| Attribute                     | Description                                                              |
|-------------------------------|--------------------------------------------------------------------------|
| `damage_to_entities`          | Damage dealt to entities hit by the laser. (Low for this entity)         |
| `max_cell_durability_to_destroy`| Maximum durability of cells the laser can destroy.                       |
| `damage_to_cells`             | Damage dealt to environment cells.                                       |
| `max_length`                  | The maximum length of the laser beam.                                    |
| `beam_radius`                 | The thickness of the laser beam.                                         |
| `hit_particle_chance`         | Chance to spawn particles when the laser hits something.                 |
| `beam_particle_chance`        | Chance to spawn particles along the laser beam.                          |
| `beam_particle_type`          | The type of particles to spawn along the beam.                           |
| `audio_enabled`               | Whether audio effects are played for the laser.                          |
| `laser_angle_add_rad`         | Additional angle applied to the laser emission in radians (90 degrees).  |