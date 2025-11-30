---
title: Snowy Rock 05 Prop
category: entities
---

---

# Snowy Rock 05 Prop

This document describes the `snowy_rock_05.xml` entity, a prop found in the overworld.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the prop.

| Attribute           | Value                                       | Description                                                                 |
| :------------------ | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `pixel_scene`       | `data/biome_impl/overworld/snowy_rock_05.png` | Path to the primary pixel scene image for the prop.                         |
| `pixel_scene_visual`| `data/biome_impl/overworld/snowy_rock_05_visual.png` | Path to the visual layer of the pixel scene, often for effects or details. |
| `offset_x`          | `-37`                                       | Horizontal offset for the prop's placement.                                 |
| `offset_y`          | `-15`                                       | Vertical offset for the prop's placement.                                   |

### LifetimeComponent
This component dictates how long the prop will exist.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `2`   | The duration in seconds the prop will last. |