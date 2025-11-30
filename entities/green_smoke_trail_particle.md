---
title: Green Smoke Trail Particle
category: guides
---

<Entity>
	<Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml">
		<SpriteParticleEmitterComponent>
		</SpriteParticleEmitterComponent>
		
		<SpriteParticleEmitterComponent
			sprite_file="data/particles/smoke_cloud_tiny_green_$[1-4].xml"
			>
		</SpriteParticleEmitterComponent>
	</Base>
</Entity>
```

---
title: Green Smoke Trail Particle
category: entities/particles
---

# Green Smoke Trail Particle

This entity defines a green smoke trail particle effect, typically used in explosions. It inherits its base functionality from `base_smoke_trail.xml` and customizes the sprite used for the smoke.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_smoke_trail.xml"`**: This indicates that the entity inherits properties and behaviors from a generic smoke trail particle. This is crucial for understanding its fundamental mechanics like lifespan, movement, and visual decay.

### SpriteParticleEmitterComponent

This component is responsible for generating and managing the visual particles.

*   **`sprite_file="data/particles/smoke_cloud_tiny_green_$[1-4].xml"`**: This is the primary customization for this specific particle. It defines the sprite files used for the green smoke. The `$[1-4]` notation suggests that the game will randomly select one of four variations of "smoke_cloud_tiny_green" sprites, adding visual variety to the trail.

## Usage

This entity is likely instantiated by other explosion or projectile entities to create a visual effect of green smoke trailing behind them. The specific parameters for emission (rate, velocity, color, etc.) are inherited from `base_smoke_trail.xml` unless overridden by additional `SpriteParticleEmitterComponent` instances (though none are present in this specific example beyond the sprite selection).