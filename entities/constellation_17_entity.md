---
title: Constellation 17 Entity
category: entities
---

# Constellation 17 Entity

This entity represents a visual element, likely a constellation or celestial pattern, used in the game's introduction. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: Inherits core properties and behaviors from a base constellation entity. This suggests shared visual or functional elements across different constellation types.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/03_01.png"`**: This is the primary attribute defining the visual aspect of this specific constellation. It points to an image file that is likely animated, creating the visual effect of the constellation.

## Usage

This entity is intended for use within the game's introductory sequences or as a decorative element in specific scenes. The `image_animation_file` is crucial for its visual representation.

```xml
<Entity serialize="0">
	<Base file="data/entities/intro/constellation_base.xml">
	  	<ParticleEmitterComponent 
			image_animation_file="data/entities/intro/03_01.png" >
		</ParticleEmitterComponent>
	</Base>
</Entity>
```