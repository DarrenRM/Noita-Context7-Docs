---
title: Wraith Arm Sprite Animations
category: entities
---

# Wraith Arm Sprite Animations

This document details the sprite animations for the Wraith Arm enemy in Noita, as defined in `wraith_arm.xml`.

## Sprite Definition

The core sprite definition for the Wraith Arm.

### Key Attributes

*   **filename**: `data/enemies_gfx/wraith_arm.png` - The path to the sprite sheet.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animations

The Wraith Arm utilizes several `RectAnimation` elements to define its visual states. Most animations share the same frame data, suggesting they are visually identical or very similar.

### Animation Details

| Animation Name | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :--- |
| `stand`        | 6           | 24          | 28           | 0.23       | 6              | 1    |
| `walk`         | 6           | 24          | 28           | 0.23       | 6              | 1    |
| `run`          | 6           | 24          | 28           | 0.23       | 6              | 1    |
| `burn`         | 6           | 24          | 28           | 0.23       | 6              | 1    |
| `fly_idle`     | 6           | 24          | 28           | 0.23       | 6              | 1    |
| `fly_move`     | 6           | 24          | 28           | 0.23       | 6              | 1    |

### Notes on Animations

*   All listed animations use the same sprite sheet region (`pos_x="0"`, `pos_y="0"`).
*   The `run`, `burn`, `fly_idle`, and `fly_move` animations are explicitly noted as being copied from `walk` in the source comments, indicating they share the exact same visual frames and timing.
*   The consistent frame dimensions and count suggest a single set of frames is reused for various actions.

```xml
<Sprite
 filename="data/enemies_gfx/wraith_arm.png"
 offset_x="12"
 offset_y="12" 
  default_animation="stand">

 <!-- stand -->
 <RectAnimation
  name="stand"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>

 <!-- walk -->
 <RectAnimation
  name="walk"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>

 <!-- run - copied from walk -->
 <RectAnimation
  name="run"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>

 <!-- burn - copied from walk -->
 <RectAnimation
  name="burn"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>
 
 <RectAnimation
  name="fly_idle"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>
 
 <RectAnimation
  name="fly_move"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="24"
  frame_height="28"
  frame_wait="0.23"
  frames_per_row="6"
  loop="1"   >
 </RectAnimation>

</Sprite>
```