---
title: Constellation 08 Entity
category: entities
---

# Constellation 08 Entity

This entity defines a visual element within Noita's introductory sequences, specifically part of the constellation series. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This attribute indicates that the entity inherits its fundamental properties and behaviors from a shared base entity file. This promotes code reuse and consistency across similar entities.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/01_04.png"`**: This is the primary customization for this entity. It specifies the image file used for the particle animation. This file likely contains a sequence of frames that, when animated, create the visual effect of the constellation.

## XML Structure

```xml
<Entity serialize="0">

	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/01_04.png" >
		</ParticleEmitterComponent>
	</Base>

</Entity>
```