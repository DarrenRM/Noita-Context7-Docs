---
title: Explosion Trail Smoke (No Spark)
category: guides
---

<Entity>
	<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">
		<SpriteParticleEmitterComponent>
		</SpriteParticleEmitterComponent>
		
		<SpriteParticleEmitterComponent
			sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml"
			>
		</SpriteParticleEmitterComponent>
		
		<ParticleEmitterComponent>
		</ParticleEmitterComponent>
		
		<ParticleEmitterComponent 
			is_emitting="0"
			>
		</ParticleEmitterComponent>
	</Base>
</Entity>
```

---
title: Explosion Trail Smoke (No Spark)
category: entities/particles
---

# Explosion Trail Smoke (No Spark)

This entity defines a specific type of smoke particle effect used in explosions, designed to leave a trail without generating sparks. It inherits its base functionality from `base_smoke_trail.xml`.

## Key Components and Attributes

### Base Entity Inheritance

*   **`<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">`**: This is the primary inheritance. All properties and behaviors are derived from this base file, which likely defines common explosion smoke trail characteristics.

### SpriteParticleEmitterComponent

This component is responsible for emitting sprite-based particles.

*   **`<SpriteParticleEmitterComponent>`**: An empty tag, suggesting it might be a placeholder or that default settings from the base file are being used.
*   **`<SpriteParticleEmitterComponent sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml">`**: This is a crucial configuration.
    *   **`sprite_file`**: Specifies the sprite sheet or particle definition to be used. The `$[1-4]` suggests it will randomly select one of four variations of `smoke_cloud_tiny` sprites, providing visual variety.

### ParticleEmitterComponent

This component handles the general emission of particles.

*   **`<ParticleEmitterComponent>`**: An empty tag, indicating default emission settings from the base file are applied.
*   **`<ParticleEmitterComponent is_emitting="0">`**: This specific instance is configured to *not* emit particles by default. This might be used in conjunction with other logic to control when this particular emitter becomes active, or it could be a remnant or a specific control mechanism within the base file's logic.

## Summary

The `explosion_trail_smoke_nospark.xml` entity customizes a base smoke trail effect by specifying the visual sprites used for the smoke particles. It leverages random selection of `smoke_cloud_tiny` sprites for variation. The presence of an `is_emitting="0"` component suggests a controlled emission behavior, likely managed by the inherited base file or other game logic.