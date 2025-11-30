---
title: Orbroom Particle Emitter 05_02
category: particles
---

# Orbroom Particle Emitter 05_02

This file defines a specific particle emitter used within the Orbrooms biome in Noita. It inherits base properties from `orbroom_base.xml` and customizes its visual appearance through a specific image animation file.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

*   **`image_animation_file`**: Specifies the image file used for the particle animation.
    *   Value: `data/particles/image_emitters/orbrooms/05_02.png`

### Base Entity

The `<Base>` tag indicates that this entity inherits properties from another XML file.

*   **`file`**: The path to the base XML file.
    *   Value: `data/particles/image_emitters/orbrooms/orbroom_base.xml`

This setup allows for shared particle emitter logic across different Orbroom variations while enabling unique visual styles for each.