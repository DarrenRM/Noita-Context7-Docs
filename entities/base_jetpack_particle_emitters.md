---
title: Base Jetpack Particle Emitters
category: entities
---

# Base Jetpack Particle Emitters

This document details the particle emitter components used for a base jetpack effect in Noita, focusing on visual effects rather than sound.

## ParticleEmitterComponent

This component handles the emission of standard particles, likely for the fiery exhaust of a jetpack.

### Key Attributes:

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `_tags`                   | "jetpack" - Identifies this component as part of a jetpack effect.          |
| `emitted_material_name`   | "rocket_particles" - Specifies the material used for the emitted particles. |
| `offset.x`, `offset.y`    | "-1", "-4" - Defines the particle emission origin relative to the entity.    |
| `x_pos_offset_min/max`    | "-1", "1" - Range for horizontal position variation of emitted particles.   |
| `y_pos_offset_max`        | "0" - Maximum vertical offset for emitted particles (no upward offset).     |
| `x_vel_min/max`           | "-7", "7" - Horizontal velocity range for emitted particles.                |
| `y_vel_min/max`           | "80", "180" - Vertical velocity range for emitted particles (upward thrust).|
| `count_min/max`           | "3", "7" - Number of particles emitted per burst.                           |
| `lifetime_min/max`        | "0.1", "0.2" - Duration each particle exists.                               |
| `create_real_particles`   | "0" - Indicates these are not physical, interactable particles.             |
| `emit_cosmetic_particles` | "1" - Ensures these particles are rendered visually.                        |
| `emission_interval_min/max_frames` | "0", "1" - Very rapid emission, creating a continuous stream.           |
| `is_emitting`             | "1" - The emitter is active.                                                |

## SpriteParticleEmitterComponent

This component emits custom sprite particles, likely for smoke or embers trailing from the jetpack.

### Key Attributes:

| Attribute                      | Description                                                                   |
| :----------------------------- | :---------------------------------------------------------------------------- |
| `_tags`                        | "jetpack" - Identifies this component as part of a jetpack effect.            |
| `sprite_file`                  | "data/particles/jetpack_smoke.xml" - Path to the custom sprite definition.    |
| `delay`                        | "0" - No delay before emission starts.                                        |
| `additive`                     | "1" - Particles are rendered additively, for a glowing effect.                |
| `randomize_position.min/max_x` | "-3", "-1" - Horizontal position variation for emitted sprites.               |
| `randomize_velocity.min/max_y` | "80", "180" - Vertical velocity range for emitted sprites (upward thrust).    |
| `count_min/max`                | "2", "5" - Number of sprites emitted per burst.                               |
| `emission_interval_min/max_frames` | "0", "1" - Very rapid emission, creating a continuous stream.               |
| `is_emitting`                  | "0" - **Note:** This emitter is initially inactive. It might be triggered by other game logic. |
| `render_back`                  | "1" - Renders these sprites behind other elements.                            |