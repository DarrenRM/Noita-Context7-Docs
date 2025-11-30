---
title: Extra Money Effect Entity
category: entities
---

# Extra Money Effect Entity

This entity defines a game effect that grants the player extra money.

## Key Components

### GameEffectComponent

This component is responsible for applying the game effect.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `effect`  | Specifies the type of effect. Set to `EXTRA_MONEY`. |
| `frames`  | The duration of the effect in frames (e.g., 600 frames is 10 seconds at 60 FPS). |