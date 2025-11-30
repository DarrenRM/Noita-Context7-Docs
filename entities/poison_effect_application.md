---
title: Poison Effect Application
category: entities
---

# Poison Effect Application

This entity defines a basic effect that applies poison to entities it interacts with.

## Key Components

### `GameEffectComponent`

This component dictates the type and duration of the game effect applied.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of effect to apply. Set to "POISON".   |
| `frames`  | The duration of the effect in game frames (720 frames ≈ 12 seconds). |