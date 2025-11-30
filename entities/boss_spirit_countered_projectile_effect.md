---
title: Boss Spirit Countered Projectile Effect
category: entities
---

# Boss Spirit Countered Projectile Effect

This entity defines the visual and particle effects applied to projectiles that have been countered by the Boss Alchemist's shield.

## Key Components

### SpriteComponent

This component defines the visual representation of the countered projectile.

| Attribute         | Description                                                              |
|-------------------|--------------------------------------------------------------------------|
| `image_file`      | Specifies the graphical asset used for the projectile's visual effect.   |
| `rect_animation`  | Defines the animation sequence to be played (e.g., "spawn").             |
| `offset_x`, `offset_y` | Adjusts the position of the sprite relative to the entity's origin. |
| `alpha`           | Controls the transparency of the sprite.                                 |

### ParticleEmitterComponent (Trail)

This component generates a continuous trail of particles behind the countered projectile.

| Attribute               | Description                                                                                             |
|-------------------------|---------------------------------------------------------------------------------------------------------|
| `emitted_material_name` | The material used for the particles (e.g., "plasma_fading_pink").                                       |
| `gravity.y`             | The vertical gravitational force applied to the particles. Set to `0.0` for no gravity.                 |
| `x_vel_min`, `x_vel_max`| Minimum and maximum horizontal velocity for emitted particles. Set to `0` for no horizontal movement. |
| `y_vel_min`, `y_vel_max`| Minimum and maximum vertical velocity for emitted particles. Set to `0` for no vertical movement.     |
| `friction`              | The amount of friction applied to the particles, affecting their movement over time.                    |
| `count_min`, `count_max`| The range for the number of particles emitted per emission.                                             |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration (in seconds) each particle will exist.                               |
| `is_trail`              | Set to `1` to indicate this emitter is for a trail effect.                                              |
| `trail_gap`             | The spacing between particles in the trail.                                                             |
| `emit_cosmetic_particles` | Set to `1` to emit particles that are purely visual and do not interact with gameplay.                |
| `is_emitting`           | Set to `1` to enable the particle emission.                                                             |

### ParticleEmitterComponent (Poof)

This component generates a burst of particles at the moment the projectile is countered, creating a "poof" effect.

| Attribute               | Description                                                                                             |
|-------------------------|---------------------------------------------------------------------------------------------------------|
| `emitted_material_name` | The material used for the particles (e.g., "plasma_fading_pink").                                       |
| `emitter_lifetime_frames` | The duration (in frames) for which this emitter will be active.                                         |
| `gravity.y`             | The vertical gravitational force applied to the particles. Set to `0.0` for no gravity.                 |
| `area_circle_radius.min`, `area_circle_radius.max` | Defines the radius of the circular area from which particles are emitted. |
| `velocity_always_away_from_center` | The speed at which particles are propelled outwards from the emission center.                     |
| `friction`              | The amount of friction applied to the particles, affecting their movement over time.                    |
| `count_min`, `count_max`| The range for the number of particles emitted per emission.                                             |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration (in seconds) each particle will exist.                               |
| `emit_cosmetic_particles` | Set to `1` to emit particles that are purely visual and do not interact with gameplay.                |
| `is_emitting`           | Set to `1` to enable the particle emission.                                                             |