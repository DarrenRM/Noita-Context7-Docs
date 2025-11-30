---
title: Constellation 07 Entity
category: entities
---

# Constellation 07 Entity

This entity defines a visual element within the game's introduction sequence, specifically related to a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This indicates that `constellation07.xml` inherits all properties and components from the `constellation_base.xml` file. This is a common practice for reusing common entity structures.

### ParticleEmitterComponent

This component is responsible for generating visual effects, likely for the constellation's appearance.

*   **`image_animation_file="data/entities/intro/01_03.png"`**: This attribute specifies the image file used for the particle animation. The particles emitted will be derived from the frames within this PNG file, creating a dynamic visual effect.

## Summary

The `constellation07.xml` entity is a simple extension of a base constellation entity. Its primary function is to define a specific visual representation for a constellation in the game's introduction by utilizing a particle emitter with a custom animation image.