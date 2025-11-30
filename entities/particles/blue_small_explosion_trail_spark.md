---
title: Blue Small Explosion Trail Spark
category: entities/particles
---

# Blue Small Explosion Trail Spark

This entity defines a small, blue spark particle effect used in explosions. It inherits its base behavior from `base_spark_trail.xml` and modifies specific velocity and emission properties.

## Key Components

### VelocityComponent

Controls the particle's movement and how it interacts with air.

*   **`air_friction`**: `14.0` - A high value indicating significant air resistance, causing sparks to slow down quickly.

### SetStartVelocityComponent

Determines the initial speed of the emitted sparks.

*   **`randomize_speed.min`**: `300` - The minimum initial speed for a spark.
*   **`randomize_speed.max`**: `900` - The maximum initial speed for a spark.

### DieIfSpeedBelowComponent

Defines the condition under which a spark particle will disappear.

*   **`min_speed`**: `30` - Sparks with a speed below this value will be removed.

### ParticleEmitterComponent (Primary)

This component is responsible for emitting the main trail of sparks.

*   **`emitted_material_name`**: `plasma_fading` - The material used for the emitted particles.
*   **`x_pos_offset_min` / `y_pos_offset_min`**: `0` - No positional offset from the emitter's origin.
*   **`x_pos_offset_max` / `y_pos_offset_max`**: `0` - No positional offset from the emitter's origin.
*   **`x_vel_min`**: `-5` - Minimum horizontal velocity for emitted sparks.
*   **`x_vel_max`**: `5` - Maximum horizontal velocity for emitted sparks.
*   **`y_vel_min`**: `-10` - Minimum vertical velocity for emitted sparks.
*   **`y_vel_max`**: `15` - Maximum vertical velocity for emitted sparks.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime progresses.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`lifetime_min`**: `0.3` - Minimum lifetime of a spark in seconds.
*   **`lifetime_max`**: `0.8` - Maximum lifetime of a spark in seconds.

### ParticleEmitterComponent (Secondary)

This component emits a secondary, shorter-lived burst of sparks, likely for a more immediate visual impact.

*   **`emitted_material_name`**: `plasma_fading` - The material used for these particles.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime progresses.
*   **`x_pos_offset_min`**: `-8` - Sparks are emitted within a small radius around the origin.
*   **`y_pos_offset_min`**: `-8` - Sparks are emitted within a small radius around the origin.
*   **`x_pos_offset_max`**: `8` - Sparks are emitted within a small radius around the origin.
*   **`y_pos_offset_max`**: `8` - Sparks are emitted within a small radius around the origin.
*   **`x_vel_min`**: `-5` - Minimum horizontal velocity for these sparks.
*   **`x_vel_max`**: `5` - Maximum horizontal velocity for these sparks.
*   **`y_vel_min`**: `-10` - Minimum vertical velocity for these sparks.
*   **`y_vel_max`**: `15` - Maximum vertical velocity for these sparks.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of these sparks in seconds.
*   **`lifetime_max`**: `0.3` - Maximum lifetime of these sparks in seconds.

```xml
<Entity>
	<Base file="data/entities/particles/particle_explosion/base_spark_trail.xml">
		<VelocityComponent
			air_friction="14.0"
			>
		</VelocityComponent>
		
		<SetStartVelocityComponent
			randomize_speed.min="300"
			randomize_speed.max="900"
			>
		</SetStartVelocityComponent>
		
		<DieIfSpeedBelowComponent
			min_speed="30"
			>
		</DieIfSpeedBelowComponent>
		
		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading"
			x_pos_offset_min="0"
			y_pos_offset_min="0"
			x_pos_offset_max="0"
			y_pos_offset_max="0"
			x_vel_min="-5"
			x_vel_max="5"
			y_vel_min="-10"
			y_vel_max="15"
			fade_based_on_lifetime="1"
			render_on_grid="1"
			lifetime_min="0.3"
			lifetime_max="0.8"
			>
		</ParticleEmitterComponent>

		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading"
			fade_based_on_lifetime="1"
			x_pos_offset_min="-8"
			y_pos_offset_min="-8"
			x_pos_offset_max="8"
			y_pos_offset_max="8"
			x_vel_min="-5"
			x_vel_max="5"
			y_vel_min="-10"
			y_vel_max="15"
			render_on_grid="1"
			lifetime_min="0.1"
			lifetime_max="0.3"
			>
		</ParticleEmitterComponent>
	</Base>
</Entity>
```