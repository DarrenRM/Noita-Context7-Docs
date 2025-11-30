---
title: Regeneration Effect Entity
category: entities
---

# Regeneration Effect Entity

This entity defines the visual and functional components for the "REGENERATION" game effect in Noita. It's primarily used to create a visual indicator and apply the regeneration buff to entities.

## Key Components

### Base Entity (`<Base file="data/entities/particles/heal.xml">`)

This indicates that the entity inherits its base properties and particle effects from the `heal.xml` file, suggesting it uses similar visual elements to healing effects.

### Sprite Particle Emitter Component (`<SpriteParticleEmitterComponent>`)

This component controls the emission of particles to create the visual effect of regeneration.

*   **`emission_interval_min_frames`**: `10` - The minimum number of frames between particle emissions.
*   **`emission_interval_max_frames`**: `20` - The maximum number of frames between particle emissions.
*   **`randomize_position_inside_hitbox`**: `1` - Particles will be emitted randomly within the entity's hitbox.

### Inherit Transform Component (`<InheritTransformComponent>`)

*   **`_enabled`**: `1` - This component is enabled, meaning the entity will inherit transformations (like position and rotation) from its parent.

### Game Effect Component (`<GameEffectComponent>`)

This is the core component that applies the actual game effect.

*   **`effect`**: `REGENERATION` - Specifies the type of game effect to apply.
*   **`frames`**: `150` - The duration of the regeneration effect in frames.

```xml
<Entity>
	<Base file="data/entities/particles/heal.xml" />
	
	<SpriteParticleEmitterComponent
		emission_interval_min_frames="10"
		emission_interval_max_frames="20"
		randomize_position_inside_hitbox="1" >
	</SpriteParticleEmitterComponent>
	
	<InheritTransformComponent _enabled="1" />	
    
    <GameEffectComponent 
        effect="REGENERATION"
        frames="150"
    >
	</GameEffectComponent >
</Entity>
```