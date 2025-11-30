---
title: Constellation 04 Entity
category: entities
---

# Constellation 04 Entity

This entity defines a visual element for the game's introduction, specifically a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: Inherits core properties and behaviors from a base constellation entity.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/01_00.png"`**: Specifies the image file used for the particle animation. This file likely contains a sequence of frames that create the visual effect of the constellation.

## XML Structure

```xml
<Entity serialize="0">

	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/01_00.png" >
		</ParticleEmitterComponent>
	</Base>

</Entity>
```