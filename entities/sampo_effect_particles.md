---
title: Sampo Effect Particles
category: entities
---

# Sampo Effect Particles

This entity defines particle effects associated with the Sampo, likely a visual flourish during its appearance or effect. It utilizes two `ParticleEmitterComponent` instances to generate different types of particles.

## Key Components

### ParticleEmitterComponent (Yellow Sparks)

This component is responsible for emitting yellow sparks.

*   **`emitted_material_name`**: `spark_yellow` - Specifies the material of the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `1.5` / `8.5` - The minimum and maximum duration (in seconds) each particle will exist.
*   **`count_min` / `count_max`**: `0` / `1` - The number of particles emitted per emission event.
*   **`area_circle_radius.max`**: `6` - The maximum radius of the circular area from which particles are emitted.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `4` / `30` - The minimum and maximum number of frames between particle emission events.
*   **`airflow_force`**: `0.5` - The force applied to particles by airflow.
*   **`attractor_force`**: `2` - The strength of any attractors affecting the particles.

### ParticleEmitterComponent (Gold Particles)

This component emits gold particles, likely for a more substantial visual effect.

*   **`emitted_material_name`**: `gold` - Specifies the material of the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `2.5` / `13.5` - The minimum and maximum duration (in seconds) each particle will exist.
*   **`count_min` / `count_max`**: `0` / `1` - The number of particles emitted per emission event.
*   **`area_circle_radius.max`**: `4` - The maximum radius of the circular area from which particles are emitted.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `4` / `30` - The minimum and maximum number of frames between particle emission events.
*   **`airflow_force`**: `0.5` - The force applied to particles by airflow.
*   **`attractor_force`**: `2` - The strength of any attractors affecting the particles.

```xml
<Entity name="unknown" >
	<InheritTransformComponent />
	
	<ParticleEmitterComponent 
		emitted_material_name="spark_yellow"
		gravity.y="0.0"
		lifetime_min="1.5"
		lifetime_max="8.5"
		count_min="0"
		count_max="1"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="6"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="2"
		emission_interval_min_frames="4"
		emission_interval_max_frames="30"
		emit_cosmetic_particles="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="gold"
		gravity.y="0.0"
		lifetime_min="2.5"
		lifetime_max="13.5"
		count_min="0"
		count_max="1"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="4"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="2"
		emission_interval_min_frames="4"
		emission_interval_max_frames="30"
		emit_cosmetic_particles="1"
		>
	</ParticleEmitterComponent>

</Entity>
```