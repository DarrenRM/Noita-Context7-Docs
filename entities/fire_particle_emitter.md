---
title: Fire Particle Emitter
category: entities
---

# Fire Particle Emitter

This entity defines the visual effect of fire particles, commonly used for burning effects in Noita. It utilizes two `ParticleEmitterComponent` instances to achieve a dynamic and persistent flame appearance.

## Key Components

### ParticleEmitterComponent (Main Emission)

This component handles the primary emission of fire particles.

*   **`emitted_material_name`**: `fire` - Specifies the material of the particles being emitted.
*   **`count_min` / `count_max`**: `6` / `8` - Determines the number of particles emitted per emission cycle.
*   **`offset.x` / `offset.y`**: `-1` / `0` - Sets a slight offset for the emission origin.
*   **`x_pos_offset_min` / `y_pos_offset_min`**: `-4` / `-4` - Defines the minimum positional spread of emitted particles.
*   **`x_pos_offset_max` / `y_pos_offset_max`**: `-2` / `4` - Defines the maximum positional spread of emitted particles.
*   **`x_vel_min` / `x_vel_max`**: `-10` / `10` - Sets the horizontal velocity range for emitted particles.
*   **`y_vel_min` / `y_vel_max`**: `-10` / `10` - Sets the vertical velocity range for emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `1.1` / `2.8` - Controls the lifespan of individual particles in seconds.
*   **`create_real_particles`**: `1` - Ensures that actual game particles are created.
*   **`emit_cosmetic_particles`**: `0` - Disables the emission of purely cosmetic particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`delay_frames`**: `2` - Introduces a short delay before the first emission.
*   **`is_emitting`**: `1` - The emitter is active.

### ParticleEmitterComponent (Trail Emission)

This component creates a trailing effect for the fire, making it appear more continuous.

*   **`emitted_material_name`**: `fire` - Specifies the material of the particles being emitted.
*   **`custom_style`**: `FIRE` - Applies a specific visual style to the emitted particles.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission cycle for the trail.
*   **`offset.x` / `offset.y`**: `-1` / `0` - Sets a slight offset for the emission origin.
*   **`x_pos_offset_min` / `y_pos_offset_min`**: `0` / `0` - No positional offset for trail particles.
*   **`x_pos_offset_max` / `y_pos_offset_max`**: `0` / `0` - No positional offset for trail particles.
*   **`is_trail`**: `1` - This emitter is configured to create a trail effect.
*   **`trail_gap`**: `1.0` - The distance between trail particles.
*   **`x_vel_min` / `x_vel_max`**: `-5` / `5` - Sets the horizontal velocity range for trail particles.
*   **`y_vel_min` / `y_vel_max`**: `-10` / `10` - Sets the vertical velocity range for trail particles.
*   **`lifetime_min` / `lifetime_max`**: `1.1` / `2.8` - Controls the lifespan of individual trail particles.
*   **`create_real_particles`**: `1` - Ensures that actual game particles are created.
*   **`emit_cosmetic_particles`**: `0` - Disables the emission of purely cosmetic particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Trail particles are emitted every frame.
*   **`delay_frames`**: `2` - Introduces a short delay before the first emission.
*   **`is_emitting`**: `1` - The emitter is active.