---
title: Circular Blue Muzzle Flash Particle
category: entities/particles
---

# Circular Blue Muzzle Flash Particle

This entity defines a circular blue muzzle flash effect, primarily used for visual feedback when a projectile is fired. It consists of a sprite animation and a particle emitter that generates sparks.

## Key Components

### SpriteComponent

This component handles the visual representation of the muzzle flash.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `image_file`          | Specifies the sprite sheet or animation definition to use.                  |
| `rect_animation`      | The name of the animation to play from the `image_file`.                    |
| `next_rect_animation` | The animation to transition to after the current one finishes.              |
| `emissive`            | Makes the sprite emit light, contributing to the glow effect.               |
| `additive`            | Uses additive blending for the sprite, enhancing the glow and transparency. |
| `kill_entity_after_finished` | Automatically destroys the entity once the sprite animation completes. |
| `offset_x`, `offset_y` | Adjusts the sprite's position relative to the entity's origin.              |

### ParticleEmitterComponent

This component generates secondary particles that contribute to the muzzle flash effect.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`   | The type of material the emitted particles will be. `spark_electric` suggests electrical sparks.           |
| `offset.x`, `offset.y`    | The origin point for particle emission relative to the entity.                                             |
| `x_pos_offset_min/max`    | The minimum and maximum horizontal offset for individual particle spawn positions.                           |
| `y_pos_offset_min/max`    | The minimum and maximum vertical offset for individual particle spawn positions.                             |
| `x_vel_min/max`           | The minimum and maximum horizontal velocity applied to emitted particles.                                    |
| `y_vel_min/max`           | The minimum and maximum vertical velocity applied to emitted particles.                                      |
| `count_min/max`           | The range for the number of particles to emit per burst.                                                   |
| `lifetime_min/max`        | The duration each emitted particle will exist. A very short lifetime creates a fleeting effect.            |
| `create_real_particles`   | If set to `0`, these are cosmetic particles that don't interact physically with the game world.            |
| `emit_cosmetic_particles` | If set to `1`, this emitter will generate cosmetic particles.                                              |
| `emission_interval_min/max_frames` | Controls the timing between particle emissions. `0` means they are emitted all at once.                |
| `is_emitting`             | Determines if the emitter is currently active. `1` means it is.                                            |