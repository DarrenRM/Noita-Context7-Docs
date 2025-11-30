---
title: Blue Explosion Trail Spark Particle
category: entities
---

# Blue Explosion Trail Spark Particle

This entity defines a particle effect used in explosions, specifically a blue spark trail. It inherits its base properties from `base_spark_trail.xml` and modifies its velocity and emission characteristics.

## Key Components and Attributes

### VelocityComponent

Controls the particle's movement and how it interacts with air.

*   **`air_friction`**: `8.0` - Determines how quickly the particle loses velocity due to air resistance. A higher value means faster deceleration.

### SetStartVelocityComponent

Defines the initial speed range for the emitted particles.

*   **`randomize_speed.min`**: `800` - The minimum initial speed of the spark.
*   **`randomize_speed.max`**: `2000` - The maximum initial speed of the spark.

### DieIfSpeedBelowComponent

Specifies a speed threshold below which the particle will be destroyed.

*   **`min_speed`**: `90` - Particles with a speed less than this value will disappear.

### ParticleEmitterComponent (Primary)

This component defines the main emission of the blue spark trail.

*   **`emitted_material_name`**: `"plasma_fading"` - The material used for the emitted particles.
*   **`x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`**: `0` - The particles are emitted directly from the entity's origin with no positional offset.
*   **`x_vel_min`, `x_vel_max`**: `-5` to `5` - Controls the horizontal velocity range of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: `-10` to `15` - Controls the vertical velocity range of emitted particles.
*   **`fade_based_on_lifetime`**: `1` - The particle's opacity will decrease as its lifetime progresses.
*   **`render_on_grid`**: `1` - The particle will be rendered on the game grid.
*   **`lifetime_min`**: `0.3` - The minimum duration (in seconds) the particle will exist.
*   **`lifetime_max`**: `0.8` - The maximum duration (in seconds) the particle will exist.

### ParticleEmitterComponent (Secondary)

This component adds a secondary, shorter-lived burst of sparks, likely for a more immediate visual impact.

*   **`emitted_material_name`**: `"plasma_fading"` - Same material as the primary emission.
*   **`fade_based_on_lifetime`**: `1` - Fades based on lifetime.
*   **`x_pos_offset_min`**: `-8`, **`y_pos_offset_min`**: `-8`, **`x_pos_offset_max`**: `8`, **`y_pos_offset_max`**: `8` - Particles are emitted within a small radius around the entity's origin.
*   **`x_vel_min`, `x_vel_max`**: `-5` to `5` - Controls the horizontal velocity range.
*   **`y_vel_min`, `y_vel_max`**: `-10` to `15` - Controls the vertical velocity range.
*   **`render_on_grid`**: `1` - Renders on the grid.
*   **`lifetime_min`**: `0.1` - Shorter minimum lifetime.
*   **`lifetime_max`**: `0.3` - Shorter maximum lifetime.

```xml
<Entity>
	<Base file="data/entities/particles/particle_explosion/base_spark_trail.xml">
		<VelocityComponent
			air_friction="8.0"
			>
		</VelocityComponent>
		
		<SetStartVelocityComponent
			randomize_speed.min="800"
			randomize_speed.max="2000"
			>
		</SetStartVelocityComponent>
		
		<DieIfSpeedBelowComponent
			min_speed="90"
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