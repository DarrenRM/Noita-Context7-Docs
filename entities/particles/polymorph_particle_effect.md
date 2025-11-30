---
title: Polymorph Particle Effect
category: entities/particles
---

# Polymorph Particle Effect

This entity defines a particle effect used for the polymorph transformation. It utilizes two `ParticleEmitterComponent`s and a `LightComponent` to create a visual representation of the transformation.

## SpriteParticleEmitterComponent

This component controls the emission of sprite-based particles.

### Key Attributes:

*   **`sprite_file`**: `data/particles/shine_03.xml` - Specifies the sprite to be used for the particles.
*   **`lifetime`**: `2` - The duration each particle exists in seconds.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1` - The initial color of the particles (white).
*   **`color_change.a`**: `-1` - The alpha value decreases over the particle's lifetime, causing it to fade out.
*   **`gravity.y`**: `30` - Applies a downward gravitational force to the particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `2` - Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: `1`, `1` - Each emission spawns a single particle.
*   **`randomize_rotation.min`, `randomize_rotation.max`**: `-3.1415`, `3.1415` - Particles are emitted with random rotations.
*   **`randomize_angular_velocity.min`, `randomize_angular_velocity.max`**: `-15`, `15` - Particles have random angular velocities.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`**: `-5`, `5` - Particles are emitted with random horizontal velocities.
*   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-5`, `5` - Particles are emitted with random vertical velocities.
*   **`is_emitting`**: `0` - This emitter is not actively emitting by default.

## ParticleEmitterComponent

This component defines the primary particle emission for the effect.

### Key Attributes:

*   **`emitted_material_name`**: `plasma_fading_pink` - The material of the particles being emitted.
*   **`lifetime_min`, `lifetime_max`**: `0.5`, `1.5` - The duration each particle exists in seconds.
*   **`count_min`, `count_max`**: `15`, `30` - The number of particles emitted per emission cycle.
*   **`area_circle_radius.max`**: `24` - Particles are emitted within a circular area.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: `2.5`, `1.9`, `0.15` - These attributes influence how particles are affected by airflow.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `1` - Particles are emitted continuously.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles, which are purely visual.
*   **`x_vel_min`, `x_vel_max`**: `-40`, `40` - The range of horizontal velocities for emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-40`, `40` - The range of vertical velocities for emitted particles.
*   **`is_emitting`**: `1` - This emitter is actively emitting.

## LightComponent

This component adds a light source to the particle effect.

### Key Attributes:

*   **`radius`**: `60` - The radius of the light's influence.
*   **`r`, `g`, `b`**: `0`, `40`, `80` - The color of the light (a dark blue).