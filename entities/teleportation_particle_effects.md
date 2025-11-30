---
title: Teleportation Particle Effects
category: entities
---

# Teleportation Particle Effects

This document describes the particle and light effects associated with teleportation in Noita, as defined in `teleportation.xml`.

## SpriteParticleEmitterComponent

This component defines the visual particles emitted during teleportation.

### Key Attributes:

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `sprite_file`             | Path to the sprite XML file used for the particles (e.g., `shine_02.xml`). |
| `lifetime`                | Duration in seconds each particle exists.                                   |
| `color.r`, `color.g`, `color.b`, `color.a` | Initial color and alpha of the particles.                                   |
| `color_change.a`          | Rate at which the alpha of particles changes over their lifetime.           |
| `gravity.y`               | Downward acceleration applied to particles.                                 |
| `velocity_slowdown`       | Factor by which particle velocity is reduced over time.                     |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls the timing between particle emissions.                             |
| `count_min`, `count_max`  | The minimum and maximum number of particles emitted per interval.           |
| `randomize_rotation.min`, `randomize_rotation.max` | Range for random initial rotation of particles.                             |
| `randomize_angular_velocity.min`, `randomize_angular_velocity.max` | Range for random initial angular velocity of particles.                     |
| `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y` | Defines the area around the emitter where particles can spawn.              |
| `randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y` | Range for random initial velocity applied to particles.                     |

## LightComponent

This component adds a light source to the entity, illuminating the surroundings.

### Key Attributes:

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `radius`  | The radius of the light's illumination.         |
| `r`, `g`, `b` | The RGB color values of the light.              |