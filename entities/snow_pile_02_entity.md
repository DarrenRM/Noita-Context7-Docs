---
title: Snow Pile 02 Entity
category: entities
---

# Snow Pile 02 Entity

This document describes the `snow_pile_02.xml` entity, representing a small snow pile prop found in the overworld.

## Key Components

### PixelSceneComponent

This component defines the visual representation and placement of the snow pile.

| Attribute        | Value                               | Description                                                                 |
| :--------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `pixel_scene`    | `data/biome_impl/overworld/snow_pile_02.png` | Path to the image file used for the snow pile's visual.                     |
| `pixel_scene_visual` | `""`                                | This attribute is empty, indicating no separate visual layer is used.       |
| `offset_x`       | `-11`                               | Horizontal offset for the pixel scene.                                      |
| `offset_y`       | `-15`                               | Vertical offset for the pixel scene.                                        |

### LifetimeComponent

This component controls how long the snow pile persists in the game world.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `2`   | The duration (in seconds) the entity exists. |