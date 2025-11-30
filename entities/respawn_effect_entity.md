---
title: Respawn Effect Entity
category: entities
---

# Respawn Effect Entity

This entity defines a game effect that causes a respawn.

## Key Components

### GameEffectComponent

This component dictates the type and duration of the game effect.

| Attribute | Description                                  |
| :-------- | :------------------------------------------- |
| `effect`  | Specifies the type of effect. Set to `RESPAWN`. |
| `frames`  | The duration of the effect in game frames (60 frames = 1 second). Set to `600` (10 seconds). |