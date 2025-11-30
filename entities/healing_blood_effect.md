---
title: Healing Blood Effect
category: entities
---

# Healing Blood Effect

This entity defines a game effect that heals the player over time, visually represented by blood.

## Key Components

### GameEffectComponent

This component governs the behavior and duration of the healing effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `HEALING_BLOOD` | Specifies the type of game effect. |
| `frames` | `600` | The duration of the effect in game frames (60 frames per second). This equates to 10 seconds. |

### InheritTransformComponent

This component is present but has no specific attributes configured, indicating it inherits default transform properties.