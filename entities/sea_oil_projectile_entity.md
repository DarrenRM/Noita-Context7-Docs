---
title: Sea Oil Projectile Entity
category: entities
---

# Sea Oil Projectile Entity

This document describes the `sea_oil.xml` entity, which defines the behavior and appearance of the "sea of oil" projectile in Noita. This entity is responsible for spawning oil particles and affecting the game environment.

## Core Components

The `sea_oil.xml` entity is composed of several key components that dictate its functionality:

### MaterialSeaSpawnerComponent

This component is responsible for spawning the "oil" material in the game world.

*   **`size.x`**: The width of the area where oil will be spawned.
*   **`size.y`**: The height of the area where oil will be spawned.
*   **`offset.x`**: Horizontal offset for the spawning area.
*   **`offset.y`**: Vertical offset for the spawning area.
*   **`speed`**: The speed at which the spawned oil moves.
*   **`noise_threshold`**: Controls the randomness or density of the spawned material.
*   **`material`**: Specifies the material to be spawned, in this case, "oil".

### LifetimeComponent

Determines how long the entity persists in the game.

*   **`lifetime`**: The duration in frames the entity will exist.

### ParticleEmitterComponent

This component manages the emission of visual particles that represent the "sea of oil".

*   **`emitted_material_name`**: The name of the material for the particles being emitted ("oil").
*   **`gravity.y`**: Vertical gravity applied to the particles.
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum lifespan of individual particles.
*   **`count_min` / `count_max`**: The minimum and maximum number of particles emitted per emission cycle.
*   **`render_on_grid`**: Whether the particles should be rendered on the game grid.
*   **`fade_based_on_lifetime`**: Controls if particles fade out as their lifetime ends.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Parameters related to how airflow affects the particles.
*   **`image_animation_file`**: The sprite sheet used for animating the particles.
*   **`image_animation_speed`**: The speed of the particle animation.
*   **`is_emitting`**: A flag to enable or disable particle emission.

### MusicEnergyAffectorComponent

This component suggests an interaction with a music or energy system within the game.

*   **`energy_target`**: Indicates the target for energy manipulation.

### AudioComponent

Handles the sound effects associated with the entity.

*   **`file`**: The audio bank file containing the sound events.
*   **`event_root`**: The root event name for the projectile's sound.
*   **`set_latest_event_position`**: Whether to set the sound's position to the entity's latest position.

```xml
<Entity name="$projectile_default" tags="projectile_player" >

	<MaterialSeaSpawnerComponent
	    size.x="300"
	    size.y="256"
	    offset.x="0"
	    offset.y="158"
	    speed="10"
	    noise_threshold="0.0"
	    material="oil" >
	</MaterialSeaSpawnerComponent>

	<LifetimeComponent
		lifetime="300">
	</LifetimeComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="oil"
		gravity.y="0.0"
		lifetime_min="6"
		lifetime_max="8"
		count_min="8"
		count_max="8"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		area_circle_radius.min="0"
		area_circle_radius.max="0"
		cosmetic_force_create="0"
		airflow_force="0.51"
		airflow_time="1.01"
		airflow_scale="0.05"
		x_pos_offset_min="0"
		x_pos_offset_max="0"
		y_pos_offset_min="0"
		y_pos_offset_max="0"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		emit_cosmetic_particles="1"
		image_animation_file="data/particles/image_emitters/sea_oil.png"
		image_animation_speed="5"
		image_animation_loop="0"
		is_emitting="1" >
	</ParticleEmitterComponent>

    <MusicEnergyAffectorComponent
    	energy_target="1">
    </MusicEnergyAffectorComponent>

	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/sea_of_oil"
		set_latest_event_position="1" >
	</AudioComponent>

</Entity>
```