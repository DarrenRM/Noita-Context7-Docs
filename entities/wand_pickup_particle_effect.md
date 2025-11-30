---
title: Wand Pickup Particle Effect
category: entities
---

# Wand Pickup Particle Effect

This entity defines the visual particle effect that appears when a wand is picked up in Noita. It's designed to create a brief, shimmering visual cue.

## Key Components

### VelocityComponent
Controls the movement and physics of the particles.

| Attribute      | Value | Description                                     |
|----------------|-------|-------------------------------------------------|
| `gravity_y`    | `0`   | Particles do not experience vertical gravity.   |
| `air_friction` | `4.0` | Moderate air friction applied to particles.     |

### SimplePhysicsComponent
Enables basic physics interactions for the particles.

### LifetimeComponent
Determines how long the particle effect persists.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `lifetime`| `10`  | The effect lasts for 10 game frames.      |

### SpriteParticleEmitterComponent
The core component responsible for generating and managing the particles.

| Attribute                     | Value   | Description                                                                 |
|-------------------------------|---------|-----------------------------------------------------------------------------|
| `sprite_file`                 | `data/particles/shine_05.xml` | Uses a pre-defined "shine" sprite for the particles.                      |
| `lifetime`                    | `5`     | Individual particles last for 5 game frames.                                |
| `color.r`, `color.g`, `color.b` | `1`     | Initial color is white (full red, green, blue).                             |
| `color.a`                     | `1`     | Initial alpha is fully opaque.                                              |
| `color_change.a`              | `-2`    | Alpha decreases over the particle's lifetime, causing it to fade out.       |
| `emission_interval_min_frames`| `1`     | Particles are emitted every frame (minimum).                                |
| `emission_interval_max_frames`| `1`     | Particles are emitted every frame (maximum).                                |
| `additive`                    | `1`     | Particles use additive blending, making them brighter when overlapping.     |
| `count_min`                   | `1`     | Emits at least 1 particle per emission.                                     |
| `count_max`                   | `2`     | Emits at most 2 particles per emission.                                     |
| `sprite_random_rotation`      | `1`     | Particles can have random rotation.                                         |
| `randomize_scale`             | `-0.1` to `0.1` | Small random variation in particle scale.                                   |
| `randomize_velocity`          | `-90` to `90` | Particles are emitted with a random velocity in X and Y directions.         |
| `randomize_position`          | `-2` to `2` | Particles spawn with a slight random offset from the origin.                |
| `randomize_animation_speed_coeff` | `0.667` to `1.0` | Random variation in the animation speed of the sprite.                      |

### LightComponent
Adds a light source to the particle effect.

| Attribute     | Value | Description                                     |
|---------------|-------|-------------------------------------------------|
| `_enabled`    | `1`   | The light component is active.                  |
| `r`, `g`, `b` | `228`, `255`, `70` | Light color is a bright yellowish-green.        |
| `radius`      | `48`  | The radius of the light emitted.                |
| `fade_out_time`| `2`   | The light fades out over 2 game frames.         |