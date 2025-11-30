---
title: Orbroom Particle Emitter 09_02
category: particles
---

# Orbroom Particle Emitter 09_02

This documentation describes a particle emitter configuration for the game Noita, specifically related to "orbrooms."

## Entity Definition

The core of this configuration is an `Entity` that inherits its base properties from `orbroom_base.xml`.

```xml
<Entity>
  <Base file="data/particles/image_emitters/orbrooms/orbroom_base.xml">
    <!-- Particle emitter configuration -->
  </Base>
</Entity>
```

## ParticleEmitterComponent

The `ParticleEmitterComponent` is responsible for defining how particles are generated and displayed.

### Key Attributes

*   **`image_animation_file`**: This attribute specifies the image file used for the particle animation. In this case, it points to `data/particles/image_emitters/orbrooms/09_02.png`. This image likely contains a sequence of frames that will be animated to create the visual effect of the particles.

```xml
<ParticleEmitterComponent image_animation_file="data/particles/image_emitters/orbrooms/09_02.png" />
```