---
title: Snowy Rock 02 Prop
category: entities
---

# Snowy Rock 02 Prop

This document describes the `snowy_rock_02.xml` entity, which represents a decorative snowy rock prop in the overworld.

## Key Components

### PixelSceneComponent
This component defines the visual representation of the prop.

| Attribute          | Value                                       | Description                                                              |
| :----------------- | :------------------------------------------ | :----------------------------------------------------------------------- |
| `pixel_scene`      | `data/biome_impl/overworld/snowy_rock_02.png` | Path to the primary pixel art for the rock.                              |
| `pixel_scene_visual` | `data/biome_impl/overworld/snowy_rock_02_visual.png` | Path to the visual layer, likely for effects or secondary details.       |
| `offset_x`         | `-17`                                       | Horizontal offset for the prop's placement.                              |
| `offset_y`         | `-9`                                        | Vertical offset for the prop's placement.                                |

### LifetimeComponent
This component determines how long the prop persists.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`  | `2`   | The duration in seconds the prop exists. |