---
title: Constellation 03 Entity
category: entities
---

# Constellation 03 Entity

This entity defines a visual element for the game's introduction, specifically a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file`**: `data/entities/intro/constellation_base.xml`
    *   This attribute indicates that the entity inherits its fundamental properties and behaviors from a shared base configuration for constellations.

### Particle Emitter Component

*   **`image_animation_file`**: `data/entities/intro/00_03.png`
    *   This specifies the image file used for animating the particles emitted by this entity. This likely controls the visual appearance and animation sequence of the constellation's stellar effects.

## XML Structure

```xml
<Entity serialize="0">

	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/00_03.png" >
		</ParticleEmitterComponent>
	</Base>

</Entity>
```