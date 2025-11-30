---
title: Damage Multiplier Effect
category: entities
---

# Damage Multiplier Effect

This entity defines a game effect that applies a damage multiplier to the player.

## Key Components

### GameEffectComponent
This component is responsible for defining the type and duration of the game effect.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | Specifies the type of effect. `DAMAGE_MULTIPLIER` indicates a damage modification. |
| `frames`  | The duration of the effect in game frames (60 frames = 1 second). In this case, 600 frames is 10 seconds. |