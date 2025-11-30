---
title: Constellation 02 Entity
category: entities
---

# Constellation 02 Entity

This entity defines a visual element for the game's introduction, specifically a "constellation" effect. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: This indicates that `Constellation02` inherits all properties and components from the `constellation_base.xml` file. This is a common practice for reusing common functionality and structure.

### ParticleEmitterComponent

*   **`image_animation_file="data/entities/intro/00_02.png"`**: This is the primary customization for this entity. It specifies the image file used for the particle animation. This file likely contains a sequence of frames that, when played, create the visual effect of a constellation.

## Summary

The `Constellation02` entity is a simple extension of a base constellation entity. Its main purpose is to define a specific visual animation for an introductory constellation effect by referencing a dedicated sprite sheet.