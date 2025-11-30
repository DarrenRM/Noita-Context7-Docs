---
title: Nolla Games Constellation Entity
category: entities
---

# Nolla Games Constellation Entity

This entity defines a visual element, likely a constellation or logo, associated with "Nolla Games" within the game's intro sequence. It inherits its base properties from `constellation_base.xml` and adds specific visual components.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: Inherits core properties and behaviors from a base constellation entity. This suggests a reusable template for similar visual elements.

### Particle Emitter Component

This component is responsible for generating visual effects, likely particles that form the "Nolla Games" constellation.

*   **`emission_chance="20"`**: Controls the probability of particles being emitted. A value of 20 suggests a moderate emission rate.
*   **`image_animation_file="data/entities/intro/nolla_games.png"`**: Specifies the image or animation file used for the emitted particles. This file likely contains the visual assets for the constellation.

## Summary

The `constellation_nolla_games.xml` entity is a straightforward extension of a base constellation entity. Its primary function is to display a visual representation of "Nolla Games" using a particle emitter that draws from a specific image file. The `emission_chance` attribute fine-tunes the visual density of the effect.