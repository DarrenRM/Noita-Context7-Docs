---
title: Miner Chef Sprite Animations
category: enemies_gfx
---

# Miner Chef Sprite Animations

This document details the sprite animations for the Miner Chef enemy in Noita, as defined in the `miner_chef.xml` file. It focuses on key attributes of the sprite and its various animations, providing a concise overview for modding purposes.

## Sprite Attributes

The main `<Sprite>` tag defines the core visual properties of the Miner Chef.

| Attribute       | Value                               | Description                                                                 |
| :-------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`      | `data/enemies_gfx/miner_chef.png`   | Path to the sprite sheet image file.                                        |
| `hotspots_filename` | `data/enemies_gfx/miner_hotspots.png` | Path to the image file defining collision/interaction hotspots.             |
| `offset_x`      | `7`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`      | `12`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the entity is idle.                   |

### Hotspots

The `<Hotspot>` tag defines specific points of interest on the sprite, often used for interactions or hit detection.

| Attribute | Value    | Description                               |
| :-------- | :------- | :---------------------------------------- |
| `color`   | `ff0000` | Color of the hotspot (likely for debugging). |
| `name`    | `hand`   | Identifier for this hotspot.              |

## Animations

The `<RectAnimation>` tags define individual animations. Each animation consists of a sequence of frames from the sprite sheet.

### Key Animation Attributes

| Attribute        | Description