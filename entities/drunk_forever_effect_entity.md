---
title: Drunk Forever Effect Entity
category: entities
---

# Drunk Forever Effect Entity

This entity defines a persistent "Drunk" status effect in Noita. It's designed to be applied to the player or other entities, causing a continuous visual and gameplay alteration.

## Key Components

### `GameEffectComponent`

This is the core component responsible for applying the status effect.

*   **`effect`**: Specifies the type of effect to apply. In this case, it's `"DRUNK"`.
*   **`frames`**: Determines the duration of the effect. A value of `"-1"` signifies that the effect is permanent (lasts forever).

### `Base` and `SpriteParticleEmitterComponent`

This entity inherits from a base particle effect (`data/entities/particles/drunk.xml`) and customizes its particle emission.

*   **`emission_interval_min_frames`**: The minimum number of frames between particle emissions. Set to `20`.
*   **`emission_interval_max_frames`**: The maximum number of frames between particle emissions. Set to `50`.
*   **`randomize_position_inside_hitbox`**: Controls whether particles are emitted randomly within the entity's hitbox. Set to `0`, meaning particles are emitted from a fixed position.

This setup suggests that the "Drunk" effect is visually represented by particles, and this entity ensures those particles are emitted with a specific frequency and placement.