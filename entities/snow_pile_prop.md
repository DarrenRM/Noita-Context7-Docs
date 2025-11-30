---
title: Snow Pile Prop
category: entities
---

# Snow Pile Prop

This document describes the `snow_pile_01.xml` entity, which represents a decorative snow pile prop found in the overworld biomes of Noita.

## Key Components

### PixelSceneComponent

This component defines the visual representation of the snow pile.

| Attribute         | Description                                                              |
|-------------------|--------------------------------------------------------------------------|
| `pixel_scene`     | Path to the image file used for the snow pile's visual.                  |
| `pixel_scene_visual` | (Empty in this case) Potentially used for additional visual effects. |
| `offset_x`        | Horizontal offset for the sprite.                                        |
| `offset_y`        | Vertical offset for the sprite.                                          |

### LifetimeComponent

This component determines how long the snow pile exists before disappearing.

| Attribute | Description                               |
|-----------|-------------------------------------------|
| `lifetime`  | The duration (in seconds) the prop lasts. |