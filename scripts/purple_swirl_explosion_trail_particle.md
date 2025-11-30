---
title: Purple Swirl Explosion Trail Particle
category: data/entities/particles
---

# Purple Swirl Explosion Trail Particle

This document describes the configuration for a specific particle effect in Noita, designed to create a slow, swirling purple trail during explosions.

## Entity Configuration

The core of this particle effect is defined within an `<Entity>` tag.

### Key Components and Attributes

This particle utilizes several components to achieve its visual and behavioral characteristics.

#### VelocityComponent

Controls the basic physics of the particle, primarily its movement in relation to gravity and air friction.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="2"`: Applies a moderate amount of air friction, slowing the particle over time.
*   `updates_velocity="1"`: Enables the velocity to be updated by other components.

#### SimplePhysicsComponent

A foundational component for physics-based entities, though its specific parameters are not detailed here, it's essential for the particle's interaction with the physics engine.

#### SetStartVelocityComponent

Determines the initial speed and direction of the emitted particles.

*   `randomize_speed.min="50"`: The minimum initial speed of the particle.
*   `randomize_speed.max="200"`: The maximum initial speed of the particle.
*   `randomize_angle.min="0"`: The minimum initial angle (in radians) for the particle's velocity.
*   `randomize_angle.max="6.283185"`: The maximum initial angle (in radians) for the particle's velocity (equivalent to 2π, a full circle).

#### ParticleEmitterComponent

This is the primary component responsible for generating and managing the visual particles.

*   `emitted_material_name="spark_purple_bright"`: Specifies the visual material of the particles being emitted.
*   `delay_frames="2"`: A short delay before the first particle is emitted.
*   `gravity.y="0"`: Particles emitted by this emitter are not affected by gravity.
*   `friction="10"`: High friction applied to emitted particles, contributing to their slow movement.
*   `count_min="0"` / `count_max="1"`: Emits either 0 or 1 particle per emission cycle, creating sparse trails.
*   `lifetime_min="0.5"` / `lifetime_max="2.5"`: The duration each individual particle exists.
*   `emit_real_particles="0"`: Indicates these are cosmetic particles, not physical entities.
*   `render_on_grid="0"`: Particles are not rendered on the game's grid.
*   `is_trail="1"`: Crucially, this marks the emitter as generating a trail effect.
*   `trail_gap="1"`: The spacing between particles in the trail.
*   `airflow_force="0.3"`: A small force applied by airflow.
*   `airflow_time="0.01"`: The duration airflow affects particles.
*   `airflow_scale="0.22"`: The intensity of the airflow effect.
*   `emit_cosmetic_particles="1"`: Ensures cosmetic particles are emitted.
*   `emission_interval_min_frames="1"` / `emission_interval_max_frames="1"`: Particles are emitted every frame, creating a continuous trail.
*   `fade_based_on_lifetime="1"`: Particles fade out as their lifetime approaches zero.
*   `is_emitting="1"`: The emitter is active and will produce particles.

#### LifetimeComponent

Defines the overall lifespan of the entity that hosts the particle emitter.

*   `lifetime="100"`: The base lifespan of the entity.
*   `randomize_lifetime.min="-75"`: Minimum randomization for the lifespan.
*   `randomize_lifetime.max="35"`: Maximum randomization for the lifespan.

#### LuaComponent

This component allows for custom scripting to control particle behavior.

*   `script_source_file="data/scripts/particles/swirl_movement.lua"`: Specifies the Lua script responsible for the swirling motion of the particles.
*   `execute_every_n_frame="1"`: The script runs every frame, allowing for dynamic movement updates.

```xml
<Entity>
	<VelocityComponent
		gravity_y="0"
		air_friction="2" 
		updates_velocity="1"
		>
	</VelocityComponent>

	<SimplePhysicsComponent>
	</SimplePhysicsComponent>
	
	<SetStartVelocityComponent
		randomize_speed.min="50"
		randomize_speed.max="200"
		randomize_angle.min="0"
		randomize_angle.max="6.283185" 
		>
	</SetStartVelocityComponent>
	
	<ParticleEmitterComponent 
		emitted_material_name="spark_purple_bright"
		delay_frames="2"
		offset.x="0"
		offset.y="0"
		gravity.y="0"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		friction="10"
		count_min="0"
		count_max="1"
		lifetime_min="0.5"
		lifetime_max="2.5"
		emit_real_particles="0"
		render_on_grid="0"
		is_trail="1"
		trail_gap="1"
		airflow_force="0.3"
		airflow_time="0.01"
		airflow_scale="0.22"
		emit_cosmetic_particles="1"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		fade_based_on_lifetime="1"
		is_emitting="1" >
	</ParticleEmitterComponent>

	<LifetimeComponent
		lifetime="100"
		randomize_lifetime.min="-75"
		randomize_lifetime.max="35"
		>
	</LifetimeComponent>

	<LuaComponent
		script_source_file="data/scripts/particles/swirl_movement.lua"
		execute_every_n_frame="1"
		>
	</LuaComponent>
</Entity>
```

```lua
-- data/scripts/particles/swirl_movement.lua
-- This script is responsible for the swirling motion of the purple trail particles.
-- The exact implementation details are not provided in the source XML,
-- but it would typically involve manipulating the particle's velocity
-- based on its position and time to create a rotational effect.
```