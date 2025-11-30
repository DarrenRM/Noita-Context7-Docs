---
title: Short Charm Effect Entity
category: entities
---

---

# Short Charm Effect Entity

This entity defines a short-duration charm effect, likely used for visual and auditory feedback when a charm spell is cast or applied. It inherits from a base charm particle entity and adds specific game effect and audio components.

## Key Components

### Base Entity Inheritance

*   **`Base file="data/entities/particles/charm.xml"`**: This indicates that `effect_charm_short.xml` inherits its fundamental properties and particle behavior from `charm.xml`. This is a common pattern for reusing particle effects.

### SpriteParticleEmitterComponent

This component controls the emission of particles associated with the charm effect.

*   **`emission_interval_min_frames="5"`**: The minimum delay in frames between particle emissions.
*   **`emission_interval_max_frames="15"`**: The maximum delay in frames between particle emissions.
*   **`randomize_position_inside_hitbox="1"`**: Particles will be emitted randomly within the entity's hitbox.

### GameEffectComponent

This component applies the actual game effect.

*   **`effect="CHARM"`**: Specifies that the applied game effect is "CHARM".
*   **`frames="3600"`**: The duration of the charm effect in frames (approximately 60 seconds at 60 FPS).

### AudioComponent

This component handles the sound associated with the charm effect.

*   **`file="data/audio/Desktop/misc.bank"`**: The audio bank containing the sound effects.
*   **`event_root="game_effect/charm"`**: The root event name for the charm sound effect within the specified bank.