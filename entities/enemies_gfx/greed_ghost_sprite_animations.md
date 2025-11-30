---
title: Greed Ghost Sprite Animations
category: entities/enemies_gfx
---

---

# Greed Ghost Sprite Animations

This document details the sprite animations for the Greed Ghost enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `Sprite` tag defines the base image and default animation.

```xml
<Sprite
 filename="data/enemies_gfx/greed_ghost.png"
 offset_x="28"
 offset_y="28"
 default_animation="appear" >
</Sprite>
```

*   **`filename`**: Path to the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's pivot point.
*   **`default_animation`**: The animation to play when the sprite is first loaded.

## Animations

### `stand` Animation

This animation defines the idle state of the Greed Ghost.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="56"
 frame_height="56"
 frame_wait="0.2"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

*   **`name`**: Identifier for the animation.
*   **`pos_x`**, **`pos_y`**: Top-left corner of the animation frames within the sprite sheet.
*   **`frame_count`**: Total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Time in seconds between frames.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet.
*   **`loop`**: `1` for looping, `0` for non-looping.

### `appear` Animation

This animation defines the Greed Ghost's appearance sequence.

```xml
<RectAnimation
 name="appear"
 pos_x="0"
 pos_y="56"
 frame_count="4"
 frame_width="56"
 frame_height="56"
 frame_wait="0.1"
 frames_per_row="4"
 next_animation="stand"
 loop="0" >
</RectAnimation>
```

*   **`name`**: Identifier for the animation.
*   **`pos_x`**, **`pos_y`**: Top-left corner of the animation frames within the sprite sheet. Note that `pos_y="56"` indicates these frames are below the `stand` frames.
*   **`frame_count`**: Total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Time in seconds between frames.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet.
*   **`next_animation`**: Specifies which animation to transition to after this one completes.
*   **`loop`**: `0` for non-looping, as this is an introductory animation.