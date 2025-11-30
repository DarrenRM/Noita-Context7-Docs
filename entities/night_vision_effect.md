---
title: Night Vision Effect
category: entities
---

# Night Vision Effect

This entity defines a game effect that grants the player night vision.

## GameEffectComponent

This component manages the core game effect.

| Attribute        | Value   | Description                                                              |
| :--------------- | :------ | :----------------------------------------------------------------------- |
| `effect`         | `CUSTOM` | Specifies that this is a custom effect.                                  |
| `custom_effect_id` | `NIGHTVISION` | A unique identifier for this custom effect.                              |
| `frames`         | `600`   | The duration of the effect in frames (600 frames = 10 seconds at 60 FPS). |

## DrugEffectModifierComponent

This component modifies the player's perception when the night vision effect is active.

| Attribute        | Value | Description