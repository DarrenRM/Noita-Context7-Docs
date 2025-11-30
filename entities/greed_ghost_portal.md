---
title: Greed Ghost Portal
category: entities
---

# Greed Ghost Portal

This entity defines a portal that spawns a "Greed Ghost" after a set duration. It primarily consists of visual effects and a component to load another entity.

## Key Components

### LightComponent
This component adds a persistent light source to the portal.

| Attribute       | Value   | Description                                     |
| --------------- | ------- | ----------------------------------------------- |
| `_enabled`      | `1`     | Enables the light component.                    |
| `radius`        | `255`   | The maximum radius of the light's influence.    |
| `fade_out_time` | `10.5`  | Duration in seconds for the light to fade out.  |
| `r`, `g`, `b`   | `130`, `83`, `222` | RGB color values for the light (purple hue). |
| `offset_y`      | `-16`   | Vertical offset of the light source.            |

### SpriteParticleEmitterComponent
This component generates a swirling particle effect around the portal.

| Attribute               | Value   | Description                                                              |
| ----------------------- | ------- | ------------------------------------------------------------------------ |
| `sprite_file`           | `data/particles/purple_whirl_0$[1-8].png` | Sprite sheet for the particles, using variations. |
| `lifetime`              | `1.5`   | Duration each particle exists in seconds.                                |
| `color.a`               | `0.75`  | Initial alpha transparency of particles.                                 |
| `color_change.a`        | `-0.8`  | Rate at which particle transparency decreases.                           |
| `velocity_slowdown`     | `0.35`  | How quickly particles lose their velocity.                               |
| `angular_velocity`      | `7.5`   | Base rotation speed of particles.                                        |
| `scale_velocity.x`, `scale_velocity.y` | `1.0075` | How quickly particles scale up.                                          |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `2`, `4` | Controls the rate of particle emission.                                  |
| `count_min`, `count_max` | `1`, `1` | Number of particles emitted per burst.                                   |
| `randomize_position`    | `-0.5` to `0.5` | Randomizes particle spawn position within a small area.                  |
| `randomize_velocity`    | `-5` to `5` | Randomizes particle initial velocity.                                    |
| `randomize_lifetime`    | `-0.2` to `0.2` | Randomizes particle lifespan.                                            |
| `randomize_angular_velocity` | `-3.5` to `3.5` | Randomizes particle rotation speed.                                      |
| `randomize_rotation`    | `-90` to `90` | Randomizes particle initial rotation.                                    |

### LoadEntitiesComponent
This component is responsible for spawning the actual "Greed Ghost" entity.

| Attribute      | Value                                       | Description                                                              |
| -------------- | ------------------------------------------- | ------------------------------------------------------------------------ |
| `count.min`, `count.max` | `1`, `1`                                    | Spawns exactly one entity.                                               |
| `timeout_frames` | `180`                                       | The portal will wait for 180 frames (3 seconds) before spawning the entity. |
| `kill_entity`  | `1`                                         | The portal entity will be destroyed after spawning the Greed Ghost.      |
| `entity_file`  | `data/entities/misc/greed_curse/greed_ghost.xml` | The path to the entity file that will be loaded.                         |