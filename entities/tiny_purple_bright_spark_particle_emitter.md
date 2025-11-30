---
title: Tiny Purple Bright Spark Particle Emitter
category: entities
---

# Tiny Purple Bright Spark Particle Emitter

This document describes the configuration for a particle emitter that generates small, bright purple sparks. This is useful for creating visual effects like magical discharges, electrical arcs, or small explosions.

## ParticleEmitterComponent

This is the core component responsible for emitting particles.

### Key Attributes:

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`   | The name of the material to be emitted. In this case, it's `spark_purple_bright`.                          |
| `offset.x`, `offset.y`    | The base offset from the entity's origin where particles are emitted. Set to `0` for no offset.            |
| `x_pos_offset_min/max`    | The minimum and maximum horizontal offset from the emission point.                                         |
| `y_pos_offset_min/max`    | The minimum and maximum vertical offset from the emission point.                                           |
| `gravity.y`               | The gravitational pull on the emitted particles. `0` means no gravity.                                     |
| `x_vel_min/max`           | The minimum and maximum horizontal velocity of emitted particles.                                          |
| `y_vel_min/max`           | The minimum and maximum vertical velocity of emitted particles.                                            |
| `count_min/max`           | The minimum and maximum number of particles emitted per emission event.                                    |
| `is_trail`                | If `1`, particles will leave a trail.                                                                      |
| `trail_gap`               | The gap between segments of the particle trail.                                                            |
| `fade_based_on_lifetime`  | If `1`, particles will fade out as their lifetime decreases.                                               |
| `lifetime_min/max`        | The minimum and maximum duration (in seconds) each particle will exist.                                    |
| `airflow_force`           | The strength of airflow affecting the particles.                                                           |
| `airflow_time`            | The duration (in seconds) airflow affects the particles.                                                   |
| `airflow_scale`           | The scaling factor for airflow effects.                                                                    |
| `create_real_particles`   | If `0`, these are cosmetic particles and don't interact physically.                                        |
| `emit_cosmetic_particles` | If `1`, particles are treated as cosmetic effects.                                                         |
| `render_on_grid`          | If `1`, particles will be rendered on the game grid.                                                       |
| `emission_interval_min/max_frames` | The minimum and maximum number of frames between particle emission events.                               |
| `is_emitting`             | If `1`, the emitter is active.                                                                             |

### Example Usage:

```xml
<Entity>
  <ParticleEmitterComponent 
		emitted_material_name="spark_purple_bright"
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
		lifetime_max="3.0"
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