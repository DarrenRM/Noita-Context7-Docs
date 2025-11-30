---
title: Shotgunner Sprite Definitions
category: entities/enemies_gfx
---

# Shotgunner Sprite Definitions

This document details the sprite and animation definitions for the "Shotgunner" enemy in Noita, as found in `shotgunner.xml`. It focuses on key attributes for modding purposes.

## Sprite Attributes

These define the base sprite image and its positioning.

| Attribute      | Value      | Description                                     |
|----------------|------------|-------------------------------------------------|
| `filename`     | `data/enemies_gfx/shotgunner.png` | Path to the main sprite image file.             |
| `hotspots_filename` | `data/enemies_gfx/shotgunner_hotspots.png` | Path to the sprite file defining collision/hitboxes. |
| `offset_x`     | `8`        | Horizontal offset for sprite placement.         |
| `offset_y`     | `7.5`      | Vertical offset for sprite placement.           |
| `default_animation` | `stand`    | The animation to play by default.               |

### Hotspots

Defines specific points on the sprite, often used for interactions or hit detection.

| Attribute | Value    | Description                               |
|-----------|----------|-------------------------------------------|
| `color`   | `ff0000` | Color of the hotspot (often red for 'hand'). |
| `name`    | `hand`   | Identifier for the hotspot.               |

## Animation Definitions

Each `<RectAnimation>` tag defines a distinct animation sequence.

### Key Animation Attributes

| Attribute        | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `name`           | The identifier for the animation (e.g., "stand", "walk", "attack").         |
| `pos_x`, `pos_y` | Starting coordinates within the sprite sheet for this animation.            |
| `frame_count`    | Total number of frames in the animation.                                    |
| `frame_width`    | Width of each individual frame.                                             |
| `frame_height`   | Height of each individual frame.                                            |
| `frame_wait`     | Time in seconds between each frame.                                         |
| `frames_per_row` | How many frames are arranged horizontally in the sprite sheet row.          |
| `loop`           | `1` for looping animations, `0` for one-time animations.                    |

### Notable Animations and Events

| Animation Name   | Key Attributes