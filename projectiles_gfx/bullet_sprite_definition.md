---
title: Bullet Sprite Definition
category: projectiles_gfx
---

# Bullet Sprite Definition

This document describes the sprite definition for the "bullet" projectile in Noita. It outlines the visual representation and animation properties.

## Sprite Attributes

The `<Sprite>` tag defines the primary visual asset for the projectile.

| Attribute      | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `default_animation` | The name of the animation to play by default.                            |
| `filename`     | The path to the image file containing the sprite frames.                 |
| `offset_x`     | The horizontal offset of the sprite's origin (0.5 is center).            |
| `offset_y`     | The vertical offset of the sprite's origin (0.5 is center).              |

## RectAnimation: fireball

The `<RectAnimation>` tag defines a specific animation sequence. In this case, it's named "fireball".

| Attribute        | Description