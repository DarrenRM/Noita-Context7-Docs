---
title: Unstable Teleportation Effect
category: entities
---

---

# Unstable Teleportation Effect

This entity defines the behavior and visual effects associated with the "Unstable Teleportation" game effect in Noita. It's primarily used to create a temporary, unpredictable teleportation hazard.

## Key Components

### Base Entity (`Base`)

*   **`file="data/entities/particles/teleportation_blast.xml"`**: This indicates that the entity inherits its foundational properties and particle effects from `teleportation_blast.xml`. This likely provides the visual "blast" or particle shower associated with the teleportation.

### Sprite Particle Emitter (`SpriteParticleEmitterComponent`)

*   **`randomize_position_inside_hitbox="1"`**: Particles emitted will have their positions randomized within the entity's hitbox, contributing to a more dynamic visual spread.

### Game Effect (`GameEffectComponent`)

This is the core component that defines the actual "Unstable Teleportation" effect.

*   **`effect="UNSTABLE_TELEPORTATION"`**: Specifies the type of game effect being applied.
*   **`frames="300"`**: The duration of the effect in frames (approximately 5 seconds at 60 FPS).
*   **`teleportation_probability="200"`**: A value representing the chance of a teleportation event occurring. Higher values mean a higher probability. The exact scale (e.g., out of 1000) is not explicitly defined here but is a common pattern in Noita.
*   **`teleportation_delay_min_frames="600"`**: The minimum delay in frames between consecutive teleportation attempts. This ensures there's a pause before another teleport can happen.

## Inheritance (`InheritTransformComponent`)

*   **`InheritTransformComponent`**: This component, when present without specific attributes, typically means the entity will inherit the position, rotation, and scale of its parent or the entity it's attached to. In this context, it suggests the effect is applied to an existing entity or placed at a specific location.

## Summary

The `effect_unstable_teleportation.xml` entity creates a temporary hazard that has a chance to teleport entities within its area of effect. It leverages particle effects for visual feedback and a `GameEffectComponent` to manage the probability and timing of these unpredictable teleports.