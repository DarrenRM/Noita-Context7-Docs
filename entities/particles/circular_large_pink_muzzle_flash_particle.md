---
title: Circular Large Pink Muzzle Flash Particle
category: entities/particles
---

# Circular Large Pink Muzzle Flash Particle

This document describes the configuration for a circular, large, pink muzzle flash particle effect in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the particle. In this case, it points to `data/particles/explosion_100_pink.xml`, indicating a pink explosion-like texture.
*   **`rect_animation`**: Defines the name of the rectangle animation to be used. Here, it's set to "explosion".
*   **`next_rect_animation`**: Specifies the name of the next animation to play after the current one finishes. Also set to "explosion", suggesting a looping or repeating animation.
*   **`emissive`**: Set to "1", meaning the particle emits light.
*   **`additive`**: Set to "1", indicating that the particle's color is added to the background, creating a glowing effect.
*   **`kill_entity_after_finished`**: Set to "1", meaning the particle entity will be automatically removed from the game once its animation is complete.

RAW:

```xml
<Entity >
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/particles/explosion_100_pink.xml"
    next_rect_animation="explosion"
    rect_animation="explosion"
	emissive="1"
    additive="1"
    kill_entity_after_finished="1"
     >
  </SpriteComponent>
</Entity>
```