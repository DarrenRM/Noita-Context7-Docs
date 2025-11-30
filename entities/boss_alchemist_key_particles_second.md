---
title: Boss Alchemist Key Particles (Second)
category: entities
---

# Boss Alchemist Key Particles (Second)

This entity defines particle effects associated with the Boss Alchemist, specifically for a secondary set of particles. It utilizes two `ParticleEmitterComponent` instances to generate different types of visual effects.

## Key Components

### InheritTransformComponent

This component is present to inherit transform properties, likely for positioning and orientation within the game world. The `_tags` indicate it's active in various states: `second`, `enabled_in_hand`, `enabled_in_world`, and `item_identified`.

### ParticleEmitterComponent (Blood Particles)

This component is responsible for emitting "blood" particles.

*   **`emitted_material_name`**: `blood` - Specifies the material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity, suggesting they might float or be influenced by other forces.
*   **`lifetime_min` / `lifetime_max`**: `1.5` / `8.5` - The duration each particle exists in seconds.
*   **`count_min` / `count_max`**: `1` / `2` - The number of particles emitted per emission event.
*   **`render_on_grid`**: `1` - Particles are rendered even when viewed on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: `24` - The maximum radius of the circular area from which particles are emitted.
*   **`cosmetic_force_create`**: `1` - Ensures these are cosmetic particles, not affecting gameplay mechanics directly.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.5` / `0.01` / `0.05` - Parameters controlling how airflow affects the particles.
*   **`attractor_force`**: `3` - A force that attracts particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `5` - The minimum and maximum number of frames between particle emission events.
*   **`emit_cosmetic_particles`**: `1` - Explicitly states that cosmetic particles are emitted.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.

### ParticleEmitterComponent (Spark Particles)

This component is responsible for emitting "spark" particles.

*   **`emitted_material_name`**: `spark_red` - Specifies the material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity.
*   **`lifetime_min` / `lifetime_max`**: `2.5` / `13.5` - The duration each particle exists in seconds.
*   **`count_min` / `count_max`**: `1` / `2` - The number of particles emitted per emission event.
*   **`render_on_grid`**: `1` - Particles are rendered even when viewed on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: `8` - The maximum radius of the circular area from which particles are emitted.
*   **`cosmetic_force_create`**: `1` - Ensures these are cosmetic particles.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.5` / `0.01` / `0.05` - Parameters controlling how airflow affects the particles.
*   **`attractor_force`**: `3` - A force that attracts particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `4` / `14` - The minimum and maximum number of frames between particle emission events.
*   **`emit_cosmetic_particles`**: `1` - Explicitly states that cosmetic particles are emitted.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.

```xml
<Entity tags="" >
	<InheritTransformComponent 
		_tags="second,enabled_in_hand,enabled_in_world,item_identified"
		>
	</InheritTransformComponent>
	
	<ParticleEmitterComponent 
		_tags="second,enabled_in_hand,enabled_in_world,item_identified"
		emitted_material_name="blood"
		gravity.y="0.0"
		lifetime_min="1.5"
		lifetime_max="8.5"
		count_min="1"
		count_max="2"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="24"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="3"
		emission_interval_min_frames="1"
		emission_interval_max_frames="5"
		emit_cosmetic_particles="1"
		is_emitting="1" 
		collide_with_grid="0"
		cosmetic_force_create="1"
		>
	</ParticleEmitterComponent>
	
	<ParticleEmitterComponent 
		_tags="second,enabled_in_hand,enabled_in_world,item_identified"
		emitted_material_name="spark_red"
		gravity.y="0.0"
		lifetime_min="2.5"
		lifetime_max="13.5"
		count_min="1"
		count_max="2"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.max="8"
		cosmetic_force_create="0"
		airflow_force="0.5"
		airflow_time="0.01"
		airflow_scale="0.05"
		attractor_force="3"
		emission_interval_min_frames="4"
		emission_interval_max_frames="14"
		emit_cosmetic_particles="1"
		collide_with_grid="0"
		cosmetic_force_create="1"
		>
	</ParticleEmitterComponent>

</Entity>
```