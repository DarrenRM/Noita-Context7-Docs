---
title: Maggot Tiny Body Sprite Data
category: entities
---

# Maggot Tiny Body Sprite Data

This document details the sprite data for the "maggot_tiny_body" enemy in Noita, focusing on its visual representation and animations.

## Sprite Definition

The primary sprite definition for the maggot's body is as follows:

```xml
<Sprite 
  filename="data/enemies_gfx/maggot_tiny_body.png" 
  offset_x="72" 
  offset_y="48" 
  default_animation="stand">
```

*   **filename**: Specifies the image file used for the sprite.
*   **offset\_x**, **offset\_y**: Define the sprite's pivot point relative to its origin.
*   **default\_animation**: Sets the animation to play when the sprite is first loaded or idle.

## Animations

The maggot tiny body has defined animations for different actions. Each animation is defined using `RectAnimation`.

### Stand Animation

This animation represents the maggot in a standing or idle state.

```xml
<RectAnimation 
  frame_count="1" 
  frame_height="96" 
  frame_wait="0.082" 
  frame_width="96" 
  frames_per_row="4" 
  name="stand" 
  pos_x="0" 
  pos_y="0" 
  >
</RectAnimation>
```

*   **name**: "stand"
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.

### Eat Animation

This animation is used when the maggot is performing an eating action.

```xml
<RectAnimation 
  frame_count="1" 
  frame_height="96" 
  frame_wait="0.082" 
  frame_width="96" 
  frames_per_row="4" 
  name="eat" 
  pos_x="0" 
  pos_y="0" 
  >
</RectAnimation>
```

*   **name**: "eat"
*   The parameters for this animation are identical to the "stand" animation, suggesting a single-frame animation for eating or that the visual difference is handled elsewhere.