---
title: Large Blue Explosion Trail Spark
category: entities
---

# Large Blue Explosion Trail Spark

This entity defines a large, blue spark particle used in explosions. It inherits its base properties from `base_spark_trail.xml` and modifies its behavior through several `ParticleEmitterComponent` instances.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_spark_trail.xml"`**: Inherits core particle trail functionality.

### Velocity Component

*   **`air_friction="8.0"`**: Controls how quickly the spark loses velocity due to air resistance. A higher value means faster deceleration.

### Die If Speed Below Component

*   **`min_speed="30"`**: The spark will be destroyed if its speed drops below this threshold. This prevents lingering, slow-moving sparks.

### Particle Emitter Components

This entity utilizes multiple `ParticleEmitterComponent` instances to control the emission of the spark material.

*   **Emitter 1:**
    *   **`emitted_material_name="plasma_fading"`**: Specifies the material that is emitted. In this case, it's a fading plasma.

*   **Emitter 2:**
    *   **`emitted_material_name="plasma_fading"`**: Same material as above.
    *   **`lifetime_max="2.4"`**: Sets the maximum lifetime of particles emitted by this component to 2.4 seconds.

*   **Emitter 3:**
    *   **`emitted_material_name="plasma_fading"`**: Same material as above.
    *   **`lifetime_max="0.6"`**: Sets the maximum lifetime of particles emitted by this component to 0.6 seconds. This likely creates a shorter-lived, more intense burst of sparks.

---
```xml
<Entity>
	<Base file="data/entities/particles/particle_explosion/base_spark_trail.xml">
		<VelocityComponent
			air_friction="8.0"
			>
		</VelocityComponent>

		<DieIfSpeedBelowComponent
			min_speed="30"
			>
		</DieIfSpeedBelowComponent>
		
		<ParticleEmitterComponent
			emitted_material_name="plasma_fading"
			>
		</ParticleEmitterComponent>
  
		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading"
			lifetime_max="2.4"
			>
		</ParticleEmitterComponent>

		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading"
			lifetime_max="0.6"
			>
		</ParticleEmitterComponent>
	</Base>
</Entity>
```