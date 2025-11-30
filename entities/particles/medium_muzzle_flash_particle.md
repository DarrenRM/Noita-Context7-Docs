---
title: Medium Muzzle Flash Particle
category: entities/particles
---

# Medium Muzzle Flash Particle

This entity defines a medium-sized muzzle flash effect, typically used for weapon projectiles. It consists of a sprite animation and a particle emitter that generates sparks.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. The `$[1-5]` indicates a sequence of 5 frames.
    *   `data/particles/muzzle_flashes/muzzle_medium_0$[1-5].png`
*   `rect_animation`: Defines the name of the animation sequence.
    *   `muzzle`
*   `next_rect_animation`: Specifies the next animation to play after the current one finishes.
    *   `muzzle`
*   `emissive`: Enables emissive lighting for the sprite, making it glow.
    *   `1`
*   `additive`: Enables additive blending, which can enhance the glow effect.
    *   `1`
*   `kill_entity_after_finished`: Ensures the entity is removed once the animation is complete.
    *   `1`
*   `offset_x`: Horizontal offset for the sprite.
    *   `5`
*   `offset_y`: Vertical offset for the sprite.
    *   `7`

## ParticleEmitterComponent

This component generates secondary particles (sparks) that accompany the muzzle flash.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to be emitted.
    *   `spark`
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Define the area where particles can be emitted relative to the emitter's position.
    *   `min: -1, -1`
    *   `max: 1, 1`
*   `x_vel_min`, `x_vel_max`: The range of horizontal velocities for the emitted particles.
    *   `min: 300`
    *   `max: 50`
*   `y_vel_min`, `y_vel_max`: The range of vertical velocities for the emitted particles.
    *   `min: 0`
    *   `max: 0`
*   `count_min`, `count_max`: The number of particles to emit per emission event.
    *   `min: 1`
    *   `max: 6`
*   `lifetime_min`, `lifetime_max`: The duration each emitted particle will exist.
    *   `min: 0.0`
    *   `max: 0.1`
*   `create_real_particles`: Determines if actual physics-simulated particles are created.
    *   `0` (cosmetic particles are used instead)
*   `emit_cosmetic_particles`: Enables the emission of cosmetic particles.
    *   `1`
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
    *   `min: 0`
    *   `max: 0` (implies continuous emission while active)
*   `is_emitting`: Whether the emitter is currently active.
    *   `1`