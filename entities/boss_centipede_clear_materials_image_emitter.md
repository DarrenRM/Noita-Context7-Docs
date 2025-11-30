---
title: Boss Centipede Clear Materials Image Emitter
category: entities
---

# Boss Centipede Clear Materials Image Emitter

This entity defines particle emitters associated with the boss centipede, specifically for visual effects related to clearing materials. It utilizes two `ParticleEmitterComponent` instances to manage the emission of particles with distinct visual properties and behaviors.

## Key Components

### ParticleEmitterComponent (First Instance)

This component is configured for cosmetic particle emission, likely for a brief visual effect.

*   **`emitted_material_name`**: `plasma_fading` - Specifies the material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.3` - Sets a very short lifespan for these particles.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `0` / `0` - Particles are emitted from a single point.
*   **`cosmetic_force_create`**: `0` - Not a forced cosmetic particle.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.251` / `1.01` / `0.05` - Parameters controlling airflow influence on particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - These are cosmetic particles.
*   **`image_animation_file`**: `data/entities/animals/boss_centipede/clear_materials_image.png` - The sprite sheet used for particle animation.
*   **`image_animation_speed`**: `8` - Controls the speed of the sprite animation.
*   **`image_animation_loop`**: `0` - The animation does not loop.
*   **`is_emitting`**: `0` - This emitter is *not* active by default.

### ParticleEmitterComponent (Second Instance)

This component is configured for active particle emission, likely for a more persistent visual effect.

*   **`emitted_material_name`**: `plasma_fading` - Specifies the material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `2` / `5` - Sets a longer lifespan for these particles.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `0` / `0` - Particles are emitted from a single point.
*   **`cosmetic_force_create`**: `0` - Not a forced cosmetic particle.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.251` / `1.01` / `0.05` - Parameters controlling airflow influence on particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - These are cosmetic particles.
*   **`image_animation_file`**: `data/entities/animals/boss_centipede/clear_materials_image_dim.png` - The sprite sheet used for particle animation (likely a dimmer version).
*   **`image_animation_speed`**: `8` - Controls the speed of the sprite animation.
*   **`image_animation_loop`**: `0` - The animation does not loop.
*   **`y_vel_min` / `y_vel_max`**: `-40` / `40` - Sets a vertical velocity range for emitted particles.
*   **`is_emitting`**: `1` - This emitter is active by default.

### LifetimeComponent

*   **`lifetime`**: `260` - Defines the total lifespan of the entity itself in seconds.

```xml
<Entity>
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading"
		gravity.y="0.0"
		lifetime_min="0.1"
		lifetime_max="0.3"
		count_min="1"
		count_max="1"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="0"
		area_circle_radius.max="0"
		cosmetic_force_create="0"
		airflow_force="0.251"
		airflow_time="1.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		image_animation_file="data/entities/animals/boss_centipede/clear_materials_image.png"
		image_animation_speed="8"
		image_animation_loop="0"
		is_emitting="0" >
	</ParticleEmitterComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="plasma_fading"
		gravity.y="0.0"
		lifetime_min="2"
		lifetime_max="5"
		count_min="1"
		count_max="1"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="0"
		area_circle_radius.max="0"
		cosmetic_force_create="0"
		airflow_force="0.251"
		airflow_time="1.01"
		airflow_scale="0.05"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		image_animation_file="data/entities/animals/boss_centipede/clear_materials_image_dim.png"
		image_animation_speed="8"
		image_animation_loop="0"
		y_vel_min="-40"
		y_vel_max="40"
		is_emitting="1" >
	</ParticleEmitterComponent>

	<LifetimeComponent
		lifetime="260" >
	</LifetimeComponent>

</Entity>
```