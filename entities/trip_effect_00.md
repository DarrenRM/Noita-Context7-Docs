---
title: Trip Effect 00
category: entities
---

# Trip Effect 00

This entity defines a custom game effect that applies visual distortions and color shifts, simulating a "trip" effect.

## GameEffectComponent

This component manages the core game effect.

| Attribute         | Value   | Description                                      |
| :---------------- | :------ | :----------------------------------------------- |
| `effect`          | `CUSTOM` | Indicates this is a custom-defined effect.       |
| `custom_effect_id`| `TRIP_00`| The unique identifier for this custom effect.    |
| `frames`          | `600`   | The duration of the effect in frames (10 seconds). |

## DrugEffectModifierComponent

This component modifies the visual properties of the screen to create the drug-like effect.

### fx_add

These attributes define the intensity of various visual distortions.

| Attribute          | Value | Description                                                              |
| :----------------- | :---- | :----------------------------------------------------------------------- |
| `distortion_amount`| `0.2` | Controls the amount of screen distortion.                                |
| `color_amount`     | `0.05`| Controls the intensity of color shifts and saturation changes.           |
| `fractals_amount`  | `0.1` | Controls the amount of fractal patterns or psychedelic visual noise.     |