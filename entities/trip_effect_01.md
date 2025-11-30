---
title: Trip Effect 01
category: entities
---

---

# Trip Effect 01

This entity defines a visual and auditory "trip" effect, likely used for psychedelic or hallucinogenic in-game events.

## GameEffectComponent

This component controls the duration and type of the game effect.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `effect`         | `CUSTOM`| Indicates a custom-defined effect.              |
| `custom_effect_id` | `TRIP_00`| A unique identifier for this specific trip effect. |
| `frames`         | `600`   | The duration of the effect in game frames (60 FPS). |

## DrugEffectModifierComponent

This component modifies visual properties to simulate a drug-induced state.

### fx_add

These attributes add to the existing visual distortion.

| Attribute          | Value | Description                                                              |
| :----------------- | :---- | :----------------------------------------------------------------------- |
| `distortion_amount`| `0.2` | Controls the intensity of visual distortion.                             |
| `color_amount`     | `0.1` | Controls the intensity of color shifts and saturation.                   |
| `fractals_amount`  | `0.3` | Controls the intensity of fractal patterns appearing in the visuals.     |