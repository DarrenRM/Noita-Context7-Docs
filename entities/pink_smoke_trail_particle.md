---
title: Pink Smoke Trail Particle
category: guides
---

<Entity>
	<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">
		<SpriteParticleEmitterComponent>
		</SpriteParticleEmitterComponent>
		
		<SpriteParticleEmitterComponent
			sprite_file="data/particles/smoke_cloud_tiny_pink_$[1-4].xml"
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
title: Pink Smoke Trail Particle
category: entities/particles
---

# Pink Smoke Trail Particle

This entity defines a specific type of smoke trail particle used in explosions, characterized by its pink color. It inherits its base functionality from `base_smoke_trail.xml` and customizes the visual appearance.

## Key Components

### Base Entity Inheritance

*   **`<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">`**: This is the primary inheritance. The pink smoke trail particle reuses the core logic and properties defined in the base smoke trail entity.

### SpriteParticleEmitterComponent

This component is responsible for emitting sprite-based particles.

*   **`<SpriteParticleEmitterComponent>`**: An empty tag, likely inheriting default sprite emitter properties from the base.
*   **`<SpriteParticleEmitterComponent sprite_file="data/particles/smoke_cloud_tiny_pink_$[1-4].xml">`**: This is the crucial customization. It specifies the sprite files to be used for the pink smoke particles. The `$[1-4]` indicates that one of four variations of `smoke_cloud_tiny_pink` sprites will be randomly chosen, adding visual variety.

### ParticleEmitterComponent

This component controls the emission of particles.

*   **`<ParticleEmitterComponent>`**: An empty tag, likely inheriting default particle emitter properties from the base.
*   **`<ParticleEmitterComponent is_emitting="0">`**: This specific instance of the particle emitter is configured to *not* emit particles by default. This suggests it might be controlled by other game logic or events, or it's a placeholder for a disabled emitter.