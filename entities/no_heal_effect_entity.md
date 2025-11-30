---
title: No Heal Effect Entity
category: entities
---

# No Heal Effect Entity

This entity defines a game effect that prevents healing.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | Specifies the type of effect. Set to `NO_HEAL`. |
| `frames`  | Duration of the effect in frames. `-1` indicates a permanent effect. |