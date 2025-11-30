---
title: Bloody Effect Entity
category: entities
---

# Bloody Effect Entity

This entity defines the "BLOODY" game effect, which applies a critical hit boost to shots.

## Key Components

### GameEffectComponent
This component governs the core game effect.

| Attribute | Value | Description |
|---|---|---|
| `effect` | `BLOODY` | Specifies the type of game effect. |
| `frames` | `600` | The duration of the effect in frames (approximately 10 seconds). |

### ShotEffectComponent
This component modifies the properties of shots fired while the effect is active.

| Attribute | Value | Description |
|---|---|---|
| `extra_modifier` | `critical_hit_boost` | Grants a boost to critical hit chance. |