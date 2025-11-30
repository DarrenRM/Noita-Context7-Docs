---
title: Exploding Corpse Shots Effect
category: entities
---

---

# Exploding Corpse Shots Effect

This entity defines a game effect that causes a corpse to explode, likely releasing projectiles.

## Key Components

### GameEffectComponent

This component governs the behavior and duration of the game effect.

*   **`effect`**: Specifies the type of effect. In this case, it's `EXPLODING_CORPSE_SHOTS`.
*   **`frames`**: The duration of the effect in game frames. A value of `600` means the effect will last for 600 frames (approximately 10 seconds at 60 FPS).

## Inheritance

*   **`InheritTransformComponent`**: This component is present but empty, indicating that the entity inherits transform properties from its parent or a base entity. This is common for effects that don't have their own unique spatial positioning or movement.

## Usage

This entity is likely used as a component attached to other entities (e.g., corpses) to trigger the "exploding corpse shots" behavior under specific conditions. The `EXPLODING_CORPSE_SHOTS` effect itself would be defined elsewhere, detailing what projectiles are spawned and how they behave.