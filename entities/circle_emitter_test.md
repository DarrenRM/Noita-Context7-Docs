---
title: Circle Emitter Test
category: entities
---

# Circle Emitter Test

This entity demonstrates a basic particle emitter configured to emit particles in a circular pattern. It's useful for testing particle emission behaviors and visual effects.

## ParticleEmitterComponent

This component controls the emission of particles.

### Key Attributes:

*   **`emitted_material_name`**: Specifies the material of the particles to be emitted. In this case, it's `"poison"`.
*   **`gravity.y`**: The gravitational pull on the emitted particles along the Y-axis. Set to `"0.0"` for no gravity.
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum duration (in seconds) each particle will exist.
*   **`x_vel_min` / `x_vel_max`**: The minimum and maximum velocity of particles along the X-axis.
*   **`y_vel_min` / `y_vel_max`**: The minimum and maximum velocity of particles along the Y-axis.
*   **`count_min` / `count_max`**: The minimum and maximum number of particles emitted per emission cycle.
*   **`render_on_grid`**: If set to `"1"`, particles will be rendered even when the camera is zoomed out.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: Defines the radius of the circular area from which particles are emitted.
*   **`airflow_force`**: Controls the strength of airflow affecting particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: The minimum and maximum number of frames between particle emissions.
*   **`velocity_always_away_from_center`**: A value that influences particles to move away from the emission center.
*   **`is_emitting`**: If set to `"1"`, the emitter is active.

```xml
<Entity>

  	<ParticleEmitterComponent 
		emitted_material_name="poison"
		gravity.y="0.0"
		lifetime_min="3"
		lifetime_max="4"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		count_min="115"
		count_max="115"
		render_on_grid="1"
		fade_based_on_lifetime="0"
		area_circle_radius.min="15"
		area_circle_radius.max="15"
		cosmetic_force_create="0"
		airflow_force="0.051"
		airflow_time="1.01"
		airflow_scale="0.03"
		emission_interval_min_frames="12"
		emission_interval_max_frames="12"
		emit_cosmetic_particles="1"
		velocity_always_away_from_center="11"
		is_emitting="1" >
	</ParticleEmitterComponent>

</Entity>
```