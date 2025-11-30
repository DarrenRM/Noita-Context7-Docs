---
title: Large Pink Explosion Trail Spark
category: entities/particles
---

# Large Pink Explosion Trail Spark

This entity defines a large, pink spark particle used in explosions. It inherits its base behavior from `base_spark_trail.xml` and customizes its visual and behavioral properties.

## Key Components

### VelocityComponent

Controls the movement and air resistance of the spark.

| Attribute     | Value | Description                               |
|---------------|-------|-------------------------------------------|
| `air_friction`| `8.0` | The amount of friction applied in the air.|

### DieIfSpeedBelowComponent

Determines when the particle should be removed from the simulation.

| Attribute   | Value | Description                                     |
|-------------|-------|-------------------------------------------------|
| `min_speed` | `30`  | The minimum speed the particle must maintain.   |

### ParticleEmitterComponent

This component is responsible for emitting new particles. This entity uses multiple instances to create a trail effect with varying lifetimes.

#### Instance 1

| Attribute             | Value             | Description                                                                 |
|-----------------------|-------------------|-----------------------------------------------------------------------------|
| `emitted_material_name` | `plasma_fading_pink` | The material of the particles being emitted.                                |

#### Instance 2

| Attribute             | Value             | Description                                                                 |
|-----------------------|-------------------|-----------------------------------------------------------------------------|
| `emitted_material_name` | `plasma_fading_pink` | The material of the particles being emitted.                                |
| `lifetime_max`        | `2.4`             | The maximum lifetime of the emitted particles in seconds.                   |

#### Instance 3

| Attribute             | Value             | Description                                                                 |
|-----------------------|-------------------|-----------------------------------------------------------------------------|
| `emitted_material_name` | `plasma_fading_pink` | The material of the particles being emitted.                                |
| `lifetime_max`        | `0.6`             | The maximum lifetime of the emitted particles in seconds.                   |

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
			emitted_material_name="plasma_fading_pink"
			>
		</ParticleEmitterComponent>
  
		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading_pink"
			lifetime_max="2.4"
			>
		</ParticleEmitterComponent>

		<ParticleEmitterComponent 
			emitted_material_name="plasma_fading_pink"
			lifetime_max="0.6"
			>
		</ParticleEmitterComponent>
	</Base>
</Entity>
```