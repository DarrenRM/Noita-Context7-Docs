---
title: Oiled Effect Entity
category: entities
---

# Oiled Effect Entity

This entity defines the "Oiled" status effect in Noita. When applied, it causes entities to become slippery and flammable.

## Key Components

### GameEffectComponent

This component manages the duration and type of the game effect.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | Specifies the type of effect, in this case, `OILED`. |
| `frames`  | The duration of the effect in game frames (7200 frames ≈ 2 minutes). |

### InheritTransformComponent

This component is present but has no configurable attributes in this specific entity. It typically handles the entity's position, rotation, and scale.