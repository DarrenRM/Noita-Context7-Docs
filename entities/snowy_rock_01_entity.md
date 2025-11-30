---
title: Snowy Rock 01 Entity
category: entities
---

---

# Snowy Rock 01 Entity

This document describes the `snowy_rock_01.xml` entity, a prop found in the overworld.

## Entity Definition

The `Entity` tag encloses all components and properties of this game object.

## Key Components

### PixelSceneComponent

This component defines the visual representation of the snowy rock.

| Attribute         | Value                                         | Description                                                                 |
| :---------------- | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `pixel_scene`     | `data/biome_impl/overworld/snowy_rock_01.png` | Path to the primary pixel art for the rock.                                 |
| `pixel_scene_visual` | `data/biome_impl/overworld/snowy_rock_01_visual.png` | Path to the visual layer, potentially for effects or secondary details. |
| `offset_x`        | `-42`                                         | Horizontal offset for the sprite's position.                                |
| `offset_y`        | `-60`                                         | Vertical offset for the sprite's position.                                  |

### LifetimeComponent

This component dictates how long the entity persists in the game world.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime` | `2`   | The entity will exist for 2 seconds.      |