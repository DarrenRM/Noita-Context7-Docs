---
title: Player Halo Light Entity
category: entities
---

# Player Halo Light Entity

This entity defines a visual effect that surrounds the player, resembling a halo. It primarily consists of a sprite, a Lua script for behavior, a light source, and a particle emitter.

## Key Components

### SpriteComponent

This component defines the visual appearance of the halo.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `image_file`   | Path to the sprite image (`data/enemies_gfx/player_halo_light.png`). |
| `offset_x`     | Horizontal offset of the sprite.                |
| `offset_y`     | Vertical offset of the sprite.                  |
| `z_index`      | Determines the rendering order (lower is further back). |

### LuaComponent

This component links the entity to a Lua script that controls its behavior.

| Attribute           | Description                                     |
|---------------------|-------------------------------------------------|
| `script_source_file`| Path to the Lua script (`data/scripts/perks/player_halo_move.lua`). |
| `execute_every_n_frame` | How often the script's logic is executed (every 1 frame). |

### LightComponent

This component creates a light source emanating from the entity.

| Attribute | Description                                     |
|-----------|-------------------------------------------------|
| `radius`  | The radius of the light effect.                 |
| `r`       | Red component of the light color.               |
| `g`       | Green component of the light color.             |
| `b`       | Blue component of the light color.              |

### ParticleEmitterComponent

This component generates particles to enhance the visual effect of the halo.

| Attribute                   | Description                                     |
|-----------------------------|-------------------------------------------------|
| `emitted_material_name`     | The material of the particles to emit (`spark_yellow`). |
| `gravity.y`                 | Vertical gravity applied to particles.          |
| `lifetime_min` / `lifetime_max` | Minimum and maximum duration of particles.      |
| `x_pos_offset_min` / `x_pos_offset_max` | Horizontal position variation for emitted particles. |
| `y_pos_offset_min` / `y_pos_offset_max` | Vertical position variation for emitted particles.   |
| `velocity_always_away_from_center` | Force pushing particles away from the emitter. |
| `count_min` / `count_max`   | Number of particles emitted per burst.          |
| `emission_interval_min_frames` / `emission_interval_max_frames` | Frame interval between particle emissions. |
| `emit_cosmetic_particles`   | Whether to emit cosmetic particles.             |
| `is_emitting`               | Whether the emitter is currently active.        |