---
title: Hourglass Master Entity
category: entities
---

---

# Hourglass Master Entity

This document details the `hourglass_master.xml` entity, which defines the behavior and appearance of the Hourglass building in Noita. It primarily focuses on its particle effects, lighting, and a Lua script for checking its broken state.

## Key Components

### ParticleEmitterComponent

This entity utilizes multiple `ParticleEmitterComponent` instances to generate various visual effects.

#### Particle Emitter 1 (Main Spark Effect)

*   **`emitted_material_name`**: `spark_blue` - The material of the particles emitted.
*   **`x_pos_offset_min`/`max`**: `1` - Small horizontal offset for particle origin.
*   **`y_pos_offset_min`/`max`**: `74` - Significant vertical offset, placing particles near the top of the hourglass.
*   **`x_vel_min`/`max`**: `-4` to `4` - Small horizontal velocity for particles.
*   **`y_vel_min`/`max`**: `-4` to `4` - Small vertical velocity for particles.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to these particles.
*   **`lifetime_min`/`max`**: `5` to `16` - Duration particles exist.
*   **`count_min`/`max`**: `4` - Number of particles emitted per interval.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime ends.
*   **`airflow_force`**: `0.211` - Strength of airflow effect on particles.
*   **`airflow_time`**: `0.81` - Duration airflow affects particles.
*   **`airflow_scale`**: `0.05` - Scale of the airflow effect.
*   **`emission_interval_min_frames`/`max_frames`**: `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - These are cosmetic particles.
*   **`image_animation_file`**: `data/particles/image_emitters/hourglass.png` - Uses a specific animation for particle appearance.
*   **`image_animation_speed`**: `1` - Speed of the particle image animation.
*   **`image_animation_loop`**: `1` - The particle animation loops.
*   **`is_emitting`**: `1` - The emitter is active.

#### Particle Emitter 2 (Area Spark Effect)

*   **`emitted_material_name`**: `spark_blue`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`/`max`**: `3` to `4`
*   **`x_pos_offset_min`/`max`**: `1`
*   **`x_vel_min`/`max`**: `0`
*   **`y_vel_min`/`max`**: `0`
*   **`count_min`/`max`**: `80` - Emits a larger burst of particles.
*   **`render_on_grid`**: `1`
*   **`fade_based_on_lifetime`**: `1`
*   **`area_circle_radius.min`/`max`**: `12` - Particles are emitted within a circular area.
*   **`cosmetic_force_create`**: `1`
*   **`collide_with_grid`**: `0` - Particles do not collide with the grid.
*   **`airflow_force`**: `0.031`
*   **`airflow_time`**: `1.01`
*   **`airflow_scale`**: `0.03`
*   **`emission_interval_min_frames`/`max_frames`**: `36` - Emits particles less frequently.
*   **`emit_cosmetic_particles`**: `1`
*   **`velocity_always_away_from_center`**: `-8` - Particles are pushed away from the center of the emission area.
*   **`render_back`**: `1` - Particles are rendered behind other elements.
*   **`is_emitting`**: `1`

#### Particle Emitter 3 (Flicker Effect)

*   **`emitted_material_name`**: `spark_blue`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`/`max`**: `1` to `4`
*   **`x_pos_offset_min`/`max`**: `1`
*   **`x_vel_min`/`max`**: `0`
*   **`y_vel_min`/`max`**: `0`
*   **`count_min`/`max`**: `1` - Emits a single particle.
*   **`render_on_grid`**: `1`
*   **`fade_based_on_lifetime`**: `1`
*   **`area_circle_radius.min`/`max`**: `12`
*   **`cosmetic_force_create`**: `1`
*   **`collide_with_grid`**: `0`
*   **`airflow_force`**: `0.031`
*   **`airflow_time`**: `1.01`
*   **`airflow_scale`**: `0.03`
*   **`emission_interval_min_frames`/`max_frames`**: `1` to `2` - Emits very frequently.
*   **`emit_cosmetic_particles`**: `1`
*   **`velocity_always_away_from_center`**: `0` - No specific velocity direction from center.
*   **`render_back`**: `1`
*   **`is_emitting`**: `1`

### LightComponent

*   **`radius`**: `180` - The radius of the light emitted.
*   **`r`, `g`, `b`**: `255`, `255`, `20` - Defines the light color as a yellowish-white.
*   **`fade_out_time`**: `0.2` - How quickly the light fades.

### LuaComponent

*   **`script_source_file`**: `data/scripts/buildings/hourglass_broken_check.lua` - Links to an external Lua script responsible for checking if the hourglass is broken.
*   **`execute_every_n_frame`**: `30` - The script is executed every 30 frames.