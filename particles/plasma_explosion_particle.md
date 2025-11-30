---
title: Plasma Explosion Particle
category: particles
---

# Plasma Explosion Particle

This document describes the `explosion_064_plasma.xml` file, which defines a visual particle effect for a plasma explosion in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play, which is "explosion" in this case.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
*   **`offset_x`**, **`offset_y`**: The center point of the sprite relative to its origin.

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_064_plasma.png" 
  offset_x="32" 
  offset_y="32" >
  </Sprite>
```

## Animation Details

The `<RectAnimation>` tag defines the specific animation sequence.

### Key Attributes:

*   **`name`**: The name of the animation, matching `default_animation` in the `<Sprite>` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: Determines if the animation should loop (0 for no loop, 1 for loop).
*   **`shrink_by_one_pixel`**: A visual effect that slightly shrinks the sprite with each frame.

```xml
<RectAnimation 
  frame_count="5" 
  frame_height="65" 
  frame_wait="0.06" 
  frame_width="65" 
  frames_per_row="5" 
  loop="0" 
  name="explosion" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```