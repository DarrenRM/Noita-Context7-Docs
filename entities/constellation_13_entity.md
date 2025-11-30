---
title: Constellation 13 Entity
category: entities
---

# Constellation 13 Entity

This entity represents a visual element, likely a constellation or star pattern, used in the game's introduction. It inherits its base properties from `constellation_base.xml` and adds specific visual effects.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This indicates that the entity inherits its fundamental properties and behaviors from a base constellation entity. This is a common practice for reusing common logic and attributes.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/02_01.png"`**: This is the primary component defining the visual effect. It utilizes a particle emitter that draws its animation frames from the specified PNG file. This suggests a visual effect composed of animated particles, likely forming the constellation.

## Summary

The `constellation13.xml` entity is a straightforward implementation that leverages inheritance for its core functionality and uses a particle emitter with a custom animation sprite to create its visual appearance. It's a good example of how to create distinct visual entities by building upon existing base entities and defining unique particle effects.