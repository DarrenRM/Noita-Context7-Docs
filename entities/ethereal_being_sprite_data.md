---
title: Ethereal Being Sprite Data
category: entities
---

# Ethereal Being Sprite Data

This document details the sprite and animation data for the Ethereal Being enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Ethereal Being.

```xml
<Sprite 
  default_animation="appear" 
  filename="data/enemies_gfx/ethereal_being.png" 
  offset_x="21" 
  offset_y="21" >
  <!-- Animation definitions follow -->
</Sprite>
```

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play when the sprite is first loaded or becomes active. Here, it's set to "appear".
*   **`filename`**: The path to the sprite sheet image file.
*   **`offset_x`**, **`offset_y`**: Adjustments to the sprite's origin point.

## Animations

The Ethereal Being utilizes two primary animations: "stand" and "appear".

### `stand` Animation

This animation likely represents the Ethereal Being's idle or default state.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="42" 
  frame_wait="0.2" 
  frame_width="42" 
  frames_per_row="4" 
  name="stand" 
  pos_x="0" 
  pos_y="1" >
</RectAnimation>
```

#### Key Attributes:

*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_height`**, **`frame_width`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`name`**: The identifier for this animation.
*   **`pos_x`**, **`pos_y`**: The starting coordinates (top-left corner) of this animation's frames within the sprite sheet.

### `appear` Animation

This animation handles the visual effect of the Ethereal Being appearing.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="43" 
  frame_wait="0.1" 
  frame_width="43" 
  frames_per_row="4" 
  loop="0" 
  name="appear" 
  next_animation="stand" 
  pos_x="0" 
  pos_y="44" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

#### Key Attributes:

*   **`frame_count`**: The total number of frames for the appearance sequence.
*   **`frame_height`**, **`frame_width`**: Dimensions of each frame.
*   **`frame_wait`**: The speed of the appearance animation.
*   **`frames_per_row`**: Frames per row in the sprite sheet for this animation.
*   **`loop`**: Set to "0", indicating this animation does not loop.
*   **`name`**: The identifier for this animation.
*   **`next_animation`**: Specifies which animation should play after this one completes ("stand" in this case).
*   **`pos_x`**, **`pos_y`**: The starting coordinates of this animation's frames within the sprite sheet. Note the `pos_y` is offset from the "stand" animation.
*   **`shrink_by_one_pixel`**: A visual effect attribute, likely causing frames to shrink slightly during the animation.