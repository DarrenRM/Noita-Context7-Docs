---
title: Orbroom Particle Emitter 05_01
category: particles
---

# Orbroom Particle Emitter 05_01

This document describes the configuration for a specific particle emitter used in the "orbrooms" set of image emitters within Noita. It defines how a particular visual effect, likely associated with an orbroom environment, is rendered using animated particles.

## Key Components

### Entity
The root element for defining an in-game entity.

### Base
Inherits properties from a base particle emitter configuration, likely `orbroom_base.xml`. This promotes reusability and consistency for orbroom-related particle effects.

### ParticleEmitterComponent
This component is responsible for the visual emission of particles.

#### Key Attributes:
*   **`image_animation_file`**: Specifies the image file containing the animation frames for the particles. In this case, it points to `data/particles/image_emitters/orbrooms/05_01.png`. This PNG file would contain a sequence of images that, when played in succession, create the visual effect.

## Summary

This XML file defines a particle emitter that utilizes an animated image sequence (`05_01.png`) to create a visual effect. It inherits common properties from a base orbroom emitter configuration, suggesting it's part of a larger system for generating orbroom-themed visual elements in the game. The primary function of this file is to link a specific animation to a particle emission system.