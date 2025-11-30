---
title: Ultrashort All Protection Effect
category: entities
---

# Ultrashort All Protection Effect

This entity defines a temporary, very short-lived protective effect that grants immunity to all damage types. It's primarily used for visual feedback and brief invincibility.

## Key Components

### `GameEffectComponent`

This component applies the actual game effect.

*   **`_tags`**: `protection_all_short`, `effect_protection_all` - Identifies the type and duration of the protection.
*   **`effect`**: `PROTECTION_ALL` - Specifies that this grants immunity to all damage.
*   **`frames`**: `50` - The duration of the effect in game frames. This is a very short duration.

### `SpriteParticleEmitterComponent`

This component handles the visual particle effect associated with the protection.

*   **`sprite_file`**: `data/particles/protection_all.xml` - Points to the particle definition for the visual effect.
*   **`delay`**: `0` - The effect starts immediately.
*   **`lifetime`**: `0` - Particles have no independent lifetime, controlled by emitter.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1` - The particles are fully white and opaque.
*   **`velocity.y`**: `-20` - Particles are emitted upwards.
*   **`gravity.y`**: `10` - Particles are affected by gravity, pulling them downwards.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10` to `25` - Controls the rate at which particles are emitted.
*   **`count_min`, `count_max`**: `1` - A single particle is emitted per interval.
*   **`randomize_position`**: `-10` to `10` on X and Y - Particles are emitted within a small radius around the entity.
*   **`additive`**: `1` - Particles use additive blending for a brighter effect.
*   **`emissive`**: `1` - Particles emit light.

## Summary

This entity is a simple implementation of a very brief "all protection" buff. It's characterized by its short `frames` duration in the `GameEffectComponent` and a distinct upward-moving, white particle effect managed by the `SpriteParticleEmitterComponent`. It's likely used in conjunction with other game events that require a momentary invulnerability.