---
title: Tiny White Spark Particle
category: entities
---

# Tiny White Spark Particle

This document describes the configuration for a small, white spark particle effect in Noita, intended for AI-assisted modding.

## ParticleEmitterComponent

This component defines the behavior and appearance of the emitted particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark_white` - Specifies the material of the particles being emitted.
*   **`offset.x`, `offset.y`**: `0` - The base offset from the entity's position.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1` to `1` - The range for random horizontal position offset of emitted particles.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1` to `1` - The range for random vertical position offset of emitted particles.
*   **`gravity.y`**: `0` - The vertical gravity applied to the particles. `0` means no gravity.
*   **`x_vel_min`, `x_vel_max`**: `-2` to `2` - The range for random horizontal velocity of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2` to `2` - The range for random vertical velocity of emitted particles.
*   **`count_min`, `count_max`**: `1` to `2` - The minimum and maximum number of particles emitted per emission.
*   **`is_trail`**: `1` - Indicates that the particles should leave a trail.
*   **`trail_gap`**: `1` - The spacing between segments of the particle trail.
*   **`fade_based_on_lifetime`**: `1` - The particle's opacity will fade as its lifetime progresses.
*   **`lifetime_min`, `lifetime_max`**: `0.6` to `1.5` - The minimum and maximum lifetime of each emitted particle in seconds.
*   **`airflow_force`**: `0.6` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.401` - The duration for which airflow affects the particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow's influence.
*   **`create_real_particles`**: `0` - Whether to create actual game entities for these particles (0 means cosmetic only).
*   **`emit_cosmetic_particles`**: `1` - Indicates that cosmetic particles should be emitted.
*   **`render_on_grid`**: `1` - Whether the particles should be rendered on the game grid.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2` to `3` - The minimum and maximum number of frames between particle emissions.
*   **`is_emitting`**: `1` - Whether the particle emitter is currently active.

```xml
<Entity>
  <ParticleEmitterComponent 
		emitted_material_name="spark_white"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-1"
		x_pos_offset_max="1"
		y_pos_offset_min="-1"
		y_pos_offset_max="1"
		gravity.y="0"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-2"
		y_vel_max="2"
		count_min="1"
		count_max="2"
		is_trail="1"
		trail_gap="1"
		fade_based_on_lifetime="1"
		lifetime_min="0.6"
		lifetime_max="1.5"
		airflow_force="0.6"
		airflow_time="0.401"
		airflow_scale="0.05"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		render_on_grid="1"
		emission_interval_min_frames="2"
		emission_interval_max_frames="3"
		is_emitting="1" >
	</ParticleEmitterComponent>
</Entity>
```