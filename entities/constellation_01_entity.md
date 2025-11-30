---
title: Constellation 01 Entity
category: entities
---

# Constellation 01 Entity

This entity defines a visual element for the game's introduction, specifically a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This attribute indicates that the entity inherits its fundamental properties and behaviors from the `constellation_base.xml` file. This promotes reusability and modularity in entity definitions.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/00_01.png"`**: This is the primary customization for this entity. It specifies the image file used for the particle emitter's animation. This file likely contains a sequence of frames that, when rendered as particles, create the visual effect of a constellation.

```xml
<Entity serialize="0">
	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/00_01.png" >
		</ParticleEmitterComponent>
	</Base>
</Entity>
```