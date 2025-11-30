---
title: Boss Centipede Shield Trail Effect
category: entities
---

# Boss Centipede Shield Trail Effect

This entity defines the visual effect that appears when the Boss Centipede's shield converts a projectile. It consists of a sprite and two particle emitters to create a trail and a poof effect.

## Key Components

### Sprite Component

This component defines the visual appearance of the entity.

*   **`image_file`**: `data/projectiles_gfx/orb_pink_ring.xml` - Specifies the graphical asset used for the effect.
*   **`offset_x`**, **`offset_y`**: `8` - Centers the sprite.
*   **`rect_animation`**: `spawn` - Indicates the animation to play.

### Particle Emitter Component (Trail)

This emitter creates a continuous trail effect.

*   **`emitted_material_name`**: `plasma_fading_pink` - The material used for the particles.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to the particles.
*   **`friction`**: `10` - High friction to slow down particles quickly.
*   **`count_min`**, **`count_max`**: `1` - Emits a single particle per emission.
*   **`lifetime_min`**: `0.05`, **`lifetime_max`**: `1.15` - Controls the duration of each particle.
*   **`is_trail`**: `1` - Marks this emitter as a trail effect.
*   **`trail_gap`**: `3` - The spacing between trail particles.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `1` - Emits particles every frame.

### Particle Emitter Component (Poof)

This emitter creates a burst of particles when the effect is initiated.

*   **`emitted_material_name`**: `plasma_fading_pink` - The material used for the particles.
*   **`emitter_lifetime_frames`**: `2` - The emitter only lasts for 2 frames.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to the particles.
*   **`area_circle_radius.min`**, **`area_circle_radius.max`**: `3` - Particles are emitted within a small circular area.
*   **`velocity_always_away_from_center`**: `10` - Particles are pushed outwards from the emission point.
*   **`friction`**: `1.5` - Moderate friction.
*   **`count_min`**: `30`, **`count_max`**: `60` - Emits a random number of particles within this range.
*   **`lifetime_min`**: `0.5`, **`lifetime_max`**: `2.0` - Controls the duration of each particle.
*   **`emit_cosmetic_particles`**: `1` - These are purely visual particles.
*   **`is_emitting`**: `1` - The emitter is active.