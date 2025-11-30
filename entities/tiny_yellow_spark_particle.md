---
title: Tiny Yellow Spark Particle
category: entities
---

# Tiny Yellow Spark Particle

This document describes the configuration for a tiny yellow spark particle effect in Noita, intended for AI-assisted modding.

## Entity Configuration

The core of this particle effect is defined by the `ParticleEmitterComponent`.

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material name of the particles to be emitted (e.g., `spark_yellow`).    |
| `offset.x`, `offset.y`    | The base offset from the entity's position where particles are emitted.     |
| `x_pos_offset_min/max`    | The minimum and maximum horizontal offset for particle spawn position.      |
| `y_pos_offset_min/max`    | The minimum and maximum vertical offset for particle spawn position.        |
| `gravity.y`               | The gravitational pull applied to the particles on the Y-axis.              |
| `x_vel_min/max`           | The minimum and maximum horizontal velocity of emitted particles.           |
| `y_vel_min/max`           | The minimum and maximum vertical velocity of emitted particles.             |
| `count_min/max`           | The minimum and maximum number of particles emitted per emission event.     |
| `is_trail`                | Whether the particles should leave a trail.                                 |
| `trail_gap`               | The gap between trail segments if `is_trail` is enabled.                    |
| `fade_based_on_lifetime`  | Whether particles should fade out as their lifetime decreases.              |
| `lifetime_min/max`        | The minimum and maximum lifetime of emitted particles in seconds.           |
| `airflow_force`           | The force applied by airflow to the particles.                              |
| `airflow_time`            | The duration for which airflow affects the particles.                       |
| `airflow_scale`           | The scaling factor for airflow's effect.                                    |
| `create_real_particles`   | Whether to create actual game physics particles (0 for cosmetic).           |
| `emit_cosmetic_particles` | Whether to emit particles that are purely visual and don't interact physically. |
| `render_on_grid`          | Whether the particles should be rendered on the game grid.                  |
| `emission_interval_min/max_frames` | The minimum and maximum frames between particle emission events.        |
| `is_emitting`             | Whether the particle emitter is currently active.                           |

```xml
<Entity>
  <ParticleEmitterComponent 
		emitted_material_name="spark_yellow"
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
		count_max="3"
		is_trail="1"
		trail_gap="1"
		fade_based_on_lifetime="1"
		lifetime_min="0.8"
		lifetime_max="2.0"
		airflow_force="1.5"
		airflow_time="0.401"
		airflow_scale="0.05"
		create_real_particles="0"
		emit_cosmetic_particles="1"
		render_on_grid="1"
		emission_interval_min_frames="1"
		emission_interval_max_frames="2"
		is_emitting="1" >
	</ParticleEmitterComponent>
</Entity>
```