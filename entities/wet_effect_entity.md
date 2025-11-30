---
title: Wet Effect Entity
category: entities
---

---

# Wet Effect Entity

This entity defines the "Wet" status effect in Noita.

## Key Components

### GameEffectComponent

This component manages the core properties of the status effect.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `effect`  | The type of effect, set to "WET".               |
| `frames`  | Duration of the effect in game frames (7200 frames ≈ 2 minutes). |

### InheritTransformComponent

This component is present but has no configurable attributes in this specific entity. It typically handles entity transformations.