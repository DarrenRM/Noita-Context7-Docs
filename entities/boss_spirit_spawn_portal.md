---
title: Boss Spirit Spawn Portal
category: entities
---

# Boss Spirit Spawn Portal

This entity defines the visual and functional components of the portal used to spawn the boss spirit. It includes lighting effects, particle emissions for visual flair, and a Lua script to manage the spawning logic.

## Key Components

### LightComponent

This component adds a light source to the entity, contributing to the visual atmosphere of the spawn portal.

| Attribute       | Value   | Description                                     |
| :-------------- | :------ | :---------------------------------------------- |
| `_enabled`      | `1`     | Enables the light component.                    |
| `radius`        | `255`   | The radius of the light's influence.            |
| `fade_out_time` | `10.5`  | How long it takes for the light to fade out.    |
| `r`, `g`, `b`   | `10`, `180`, `222` | The RGB color values of the light (cyan hue). |

### SpriteParticleEmitterComponent

This component generates visual particles that create a swirling or ethereal effect around the portal.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/whirl_0$[1-8].png`  | The sprite files used for the particles (animated whirl sprites).           |
| `sprite_centered`         | `1`                                 | Centers the sprite on its origin.                                           |
| `delay`                   | `0`                                 | No initial delay before particle emission.                                  |
| `lifetime`                | `1.5`                               | The lifespan of each particle in seconds.                                   |
| `color.a`                 | `0.75`                              | Initial alpha transparency of the particles.                                |
| `color_change.a`          | `-0.8`                              | How the alpha transparency changes over the particle's lifetime (fades out). |
| `velocity_slowdown`       | `0.35`                              | How quickly particles lose velocity.                                        |
| `angular_velocity`        | `7.5`                               | The base angular velocity of the particles.                                 |
| `scale_velocity.x`, `scale_velocity.y` | `1.0075`                            | How the scale of particles changes over their lifetime (slightly grows).    |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `2`, `4`                            | The frame interval between particle emissions.                              |
| `count_min`, `count_max`  | `1`, `1`                            | The number of particles emitted per interval.                               |
| `randomize_position`      | `-0.5` to `0.5` (x/y)               | Randomizes the emission position within a small area.                       |
| `randomize_velocity`      | `-5` to `5` (x/y)                   | Randomizes the initial velocity of particles.                               |
| `randomize_lifetime`      | `-0.2` to `0.2`                     | Randomizes the lifespan of particles.                                       |
| `randomize_angular_velocity` | `-3.5` to `3.5`                     | Randomizes the angular velocity of particles.                               |
| `randomize_rotation`      | `-90` to `90`                       | Randomizes the initial rotation of particles.                               |

### LuaComponent

This component links the entity to a Lua script that handles the core logic of spawning the boss spirit.

| Attribute           | Value                                    | Description                                                              |
| :------------------ | :--------------------------------------- | :----------------------------------------------------------------------- |
| `script_source_file` | `data/entities/animals/boss_spirit/spawn_spirit.lua` | The path to the Lua script responsible for spawning.                     |
| `execute_every_n_frame` | `180`                                    | The script will execute its logic every 180 frames (approximately 3 seconds). |