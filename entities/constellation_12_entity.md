---
title: Constellation 12 Entity
category: entities
---

# Constellation 12 Entity

This entity represents a visual element within the game's introduction sequence, specifically a "constellation." It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This indicates that `constellation12.xml` inherits all properties and components from the `constellation_base.xml` file. This is a common practice for reusing common entity structures.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/02_00.png"`**: This is the primary customization for this entity. It specifies the image file used for the particle animation. This file likely contains a sequence of frames that, when animated, create the visual effect of a constellation.

## Summary

The `constellation12.xml` entity is a simple extension of a base constellation entity. Its core functionality and appearance are defined by the inherited `constellation_base.xml`, with its unique visual characteristic being the specific animation sequence defined by `02_00.png` in its `ParticleEmitterComponent`.