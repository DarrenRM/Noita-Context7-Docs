---
title: Constellation 14 Entity
category: entities
---

# Constellation 14 Entity

This entity defines a visual element, likely part of an introductory sequence or constellation display in Noita. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This indicates that the entity inherits its fundamental properties and behaviors from a shared base file for constellations.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/02_02.png"`**: This is the primary customization for this specific constellation. It specifies the image file used for the particle animation, suggesting a visual effect tied to this particular constellation.

## XML Structure

```xml
<Entity serialize="0">

	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/02_02.png" >
		</ParticleEmitterComponent>
	</Base>

</Entity>
```