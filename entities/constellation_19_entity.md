---
title: Constellation 19 Entity
category: entities
---

# Constellation 19 Entity

This entity defines a visual element, likely a constellation or celestial pattern, used in the game's introduction. It inherits its base properties from `constellation_base.xml` and customizes its visual appearance through a particle emitter.

## Key Attributes

*   **`serialize`**: Set to `0`, indicating this entity is not intended to be serialized (saved/loaded).
*   **`Base`**: Specifies the base entity file from which this entity inherits properties.
    *   **`file`**: Points to `data/entities/intro/constellation_base.xml`.

## ParticleEmitterComponent

This component is responsible for generating visual effects.

*   **`image_animation_file`**: Defines the sprite sheet or animation file used for the particles.
    *   **Value**: `data/entities/intro/03_03.png`