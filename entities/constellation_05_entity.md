---
title: Constellation 05 Entity
category: entities
---

# Constellation 05 Entity

This entity defines a visual element for the game's introduction sequence, specifically a constellation. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through an animated particle effect.

## Key Components

### Base Entity

*   **`file="data/entities/intro/constellation_base.xml"`**: Inherits core properties and behaviors from a base constellation entity. This is crucial for maintaining consistency across different constellation types.

### Particle Emitter Component

*   **`image_animation_file="data/entities/intro/01_01.png"`**: Specifies the image file used for the particle animation. This file likely contains a sequence of frames that create the visual effect of the constellation.

## Usage

This entity is intended for use within the game's introductory sequences, contributing to the visual storytelling and atmosphere. It's a simple entity that relies heavily on its inherited base and the visual assets provided by the particle emitter.