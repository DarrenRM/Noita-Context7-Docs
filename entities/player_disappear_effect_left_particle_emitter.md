---
title: Player Disappear Effect (Left) Particle Emitter
category: entities
---

---

# Player Disappear Effect (Left) Particle Emitter

This entity defines a particle emitter responsible for the visual effect of the player disappearing on the left side. It inherits its base functionality from `player_disappear_effect_right.xml` and customizes the particle animation.

## Key Components

### Base Entity

*   **Inheritance:** The entity inherits from `data/entities/particles/image_emitters/player_disappear_effect_right.xml`. This means it shares most of its properties with the right-side disappear effect, with specific overrides for the particle animation.

### ParticleEmitterComponent

This component controls the emission of particles for the visual effect.

*   **`offset.x`**: `1`
    *   Specifies a horizontal offset for the particle emission.
*   **`image_animation_file`**: `data/particles/image_emitters/player_disappear_left.png`
    *   The image file containing the animation frames for the disappearing player effect on the left side. This is the primary differentiator from the right-side effect.