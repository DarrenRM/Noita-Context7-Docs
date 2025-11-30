---
title: Yellow Directional Blood Splatter 3 Particle
category: particles
---

# Yellow Directional Blood Splatter 3 Particle

This document describes the configuration for a specific particle effect in Noita, representing a directional yellow blood splatter.

## Sprite Configuration

The primary visual component of this particle is defined by its sprite.

### Sprite Attributes

| Attribute     | Value                                                | Description                                                                 |
|---------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| `filename`    | `data/particles/bloodsplatters/bloodsplatter_yellow_3.png` | The image file used for the particle's visual representation.               |
| `offset_x`    | `8`                                                  | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `8`                                                  | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `smoke`                                              | The name of the default animation to play when the particle is spawned.     |

## Animation Configuration

This particle utilizes a `RectAnimation` to define its visual sequence.

### RectAnimation Attributes

| Attribute       | Value   | Description