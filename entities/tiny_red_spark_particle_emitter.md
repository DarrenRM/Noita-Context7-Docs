---
title: Tiny Red Spark Particle Emitter
category: entities
---

# Tiny Red Spark Particle Emitter

This entity defines a particle emitter that generates small, red sparks. It's designed to be used as a visual effect, likely attached to other entities or spells.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

*   **`emitted_material_name`**: `spark_red` - Specifies the material of the particles being emitted.
*   **`offset.x`, `offset.y`**: `0` - The base offset from the emitter's position.
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-8` to `8` - The range for random horizontal offset of emitted particles.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-8` to `8` - The range for random vertical offset of emitted particles.
*   **`gravity.y`**: `0` - The particles are not affected by gravity in the Y-axis.
*   **`x_vel_min`, `x_vel_max`**: `-2` to `2` - The range for random horizontal velocity of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-2` to `2` - The range for random vertical velocity of emitted particles.
*   **`count_min`, `count_max`**: `1` to `3` - The number of particles emitted per emission cycle.
*   **`lifetime_min`, `lifetime_max`**: `0.8` to `2.0` - The duration (in seconds) each individual particle will exist.
*   **`airflow_force`**: `1.5` - The strength of airflow affecting the particles.
*   **`airflow_time`**: `0.401` - The duration (in seconds) airflow is applied.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow.
*   **`emit_cosmetic_particles`**: `1` - Indicates that these are cosmetic particles, not affecting gameplay directly.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` to `2` - The minimum and maximum frames between particle emissions.
*   **`is_emitting`**: `1` - The emitter is active and will produce particles.

### LifetimeComponent

*   **`lifetime`**: `300` - The total duration (in seconds) this entity (the emitter itself) will exist.

```xml
<Entity>
	<InheritTransformComponent />
	
  <ParticleEmitterComponent 
		emitted_material_name="spark_red"
		offset.x="0"
		offset.y="0"
		x_pos_offset_min="-8"
		x_pos_offset_max="8"
		y_pos_offset_min="-8"
		y_pos_offset_max="8"
		gravity.y="0"
		x_vel_min="-2"
		x_vel_max="2"
		y_vel_min="-2"
		y_vel_max="2"
		count_min="1"
		count_max="3"
		is_trail="0"
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
	
	<LifetimeComponent
		lifetime="300"
		>
	</LifetimeComponent>
</Entity>
```