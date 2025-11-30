---
title: Constellation 16 Entity
category: entities
---

# Constellation 16 Entity

This entity defines a visual element for the game's introduction sequence, specifically a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: Inherits core properties and behaviors from a base constellation entity. This promotes reusability and consistency for introductory visual elements.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/03_00.png"`**: Specifies the image file used for the particle animation. This file likely contains a sequence of frames that, when animated, create the visual effect of the constellation.

## XML Structure

```xml
<Entity serialize="0">

	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/03_00.png" >
		</ParticleEmitterComponent>
	</Base>

</Entity>
```