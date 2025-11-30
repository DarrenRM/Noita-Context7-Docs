---
title: Orbroom Particle Emitter 09_01
category: particles
---

# Orbroom Particle Emitter 09_01

This documentation describes the configuration for a specific particle emitter used in Noita, likely associated with "orbrooms."

## ParticleEmitterComponent

This component defines the behavior and appearance of the particle emitter.

### Key Attributes:

*   **`image_animation_file`**: Specifies the image file used for the particle animation.
    *   Value: `data/particles/image_emitters/orbrooms/09_01.png`

## Base Entity

This particle emitter inherits its base properties from `orbroom_base.xml`. This suggests a common set of behaviors and visual styles for orbroom-related particles.

```xml
<Entity ><Base file="data/particles/image_emitters/orbrooms/orbroom_base.xml">
  <ParticleEmitterComponent image_animation_file="data/particles/image_emitters/orbrooms/09_01.png" />
</Base></Entity>
```