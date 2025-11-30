---
title: Teleportitis Effect Entity
category: entities
---

# Teleportitis Effect Entity

This entity defines the behavior and properties of the "Teleportitis" game effect in Noita.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | The name of the game effect to apply.     |
| `frames`  | The duration of the effect in frames (600 frames = 10 seconds). |

### InheritTransformComponent

This component is present but has no specific configurable attributes in this entity, indicating it inherits standard transform properties.