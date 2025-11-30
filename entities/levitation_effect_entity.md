---
title: Levitation Effect Entity
category: entities
---

# Levitation Effect Entity

This entity defines the visual and functional components for the levitation effect in Noita. It primarily utilizes a particle emitter to create the visual representation of levitation and a `GameEffectComponent` to apply the actual levitation status to entities.

## Key Components

### Base Entity (`data/entities/particles/levitation.xml`)

This section inherits from a base particle entity, defining the visual aspects of the levitation effect.

*   **`SpriteParticleEmitterComponent`**: Controls the emission of particles that form the levitation visual.
    *   `emission_interval_min_frames`: Minimum frames between particle emissions.
    *   `emission_interval_max_frames`: Maximum frames between particle emissions.
    *   `randomize_position_inside_hitbox`: Whether particle positions are randomized within the entity's hitbox.

### `InheritTransformComponent`

This component ensures that the levitation effect's transform (position, rotation, scale) is inherited from the entity it's applied to.

### `GameEffectComponent`

This is the core component that applies the levitation status.

*   `effect`: Specifies the type of game effect to apply. In this case, it's `"LEVITATION"`.
*   `frames`: The duration in frames for which the levitation effect will last.

```xml
<Entity>
	<Base file="data/entities/particles/levitation.xml" >
		<SpriteParticleEmitterComponent
		    emission_interval_min_frames="5"
    		emission_interval_max_frames="15"
			randomize_position_inside_hitbox="1"  >
		</SpriteParticleEmitterComponent>
	</Base>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <GameEffectComponent 
        effect="LEVITATION"
        frames="600" >
	</GameEffectComponent>
</Entity>
```