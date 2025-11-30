---
title: Thundermage Emissive Sprite Animations
category: data/enemies_gfx/
---

# Thundermage Emissive Sprite Animations

This document details the sprite animations for the Thundermage enemy, specifically focusing on its emissive graphical representation. This information is crucial for AI-assisted modding to understand and manipulate the visual behavior of this entity.

## Sprite Definition

The core sprite definition for the Thundermage emissive is as follows:

```xml
<Sprite 
  filename="data/enemies_gfx/thundermage_emissive.png" 
  offset_x="9" 
  offset_y="19"
  default_animation="stand" >
  
  <!-- Animation definitions follow -->

</Sprite>
```

*   **`filename`**: Specifies the texture file used for the sprite.
*   **`offset_x`**, **`offset_y`**: Define the sprite's pivot point relative to its graphical origin.
*   **`default_animation`**: Sets the animation to play by default when the sprite is loaded.

## Key Animations

The Thundermage has several distinct animations defined, each with specific properties.

### `stand` Animation

This is the default idle animation for the Thundermage.

```xml
  <RectAnimation 
    frame_count="8" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="stand" 
    pos_x="0" 
    pos_y="1" >
  </RectAnimation>
```

*   **`frame_count`**: Total number of frames in this animation.
*   **`frame_height`**, **`frame_width`**: Dimensions of each individual frame.
*   **`frame_wait`**: Delay between frames in seconds.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation frames within the sprite sheet.

### `walk` Animation

Represents the Thundermage's walking movement.

```xml
  <RectAnimation 
    frame_count="8" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="walk" 
    pos_x="0" 
    pos_y="26" >
  </RectAnimation>
```

*   Shares many properties with `stand`, but uses a different vertical slice (`pos_y="26"`) of the sprite sheet.

### `run` Animation

Similar to `walk`, likely for faster movement.

```xml
  <RectAnimation 
    frame_count="8" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="run" 
    pos_x="0" 
    pos_y="26" >
  </RectAnimation>
```

*   Currently uses the same sprite sheet coordinates as `walk`.

### `burn` Animation

Visual representation when the Thundermage is on fire.

```xml
  <RectAnimation 
    frame_count="8" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="burn" 
    pos_x="0" 
    pos_y="26" >
  </RectAnimation>
```

*   Also shares sprite sheet coordinates with `walk` and `run`.

### `attack` Animation

Animation for a melee or close-range attack.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="20" 
    frames_per_row="8" 
    has_offset="1" 
    loop="0" 
    name="attack" 
    offset_x="10" 
    offset_y="19" 
    pos_x="0" 
    pos_y="51" >
  </RectAnimation>
```

*   **`frame_count`**: Shorter, 6 frames.
*   **`frame_width`**: Slightly wider (20 pixels).
*   **`has_offset="1"`**: Indicates custom offsets are applied for this animation.
*   **`loop="0"`**: This animation does not loop.
*   **`offset_x`**, **`offset_y`**: Custom offsets for this specific animation.

### `fly_move` Animation

Represents the Thundermage's flying movement.

```xml
  <RectAnimation 
    frame_count="4" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="fly_move" 
    pos_x="0" 
    pos_y="76" >
  </RectAnimation>
```

*   **`frame_count`**: Shorter, 4 frames.
*   **`pos_y`**: Uses a different section of the sprite sheet (`pos_y="76"`).

### `fly_idle` Animation

Idle animation while flying.

```xml
  <RectAnimation 
    frame_count="4" 
    frame_height="24" 
    frame_wait="0.09" 
    frame_width="18" 
    frames_per_row="8" 
    name="fly_idle" 
    pos_x="0" 
    pos_y="76" >
  </RectAnimation>
```

*   Shares sprite sheet coordinates with `fly_move`.

### `attack_ranged` Animation

Animation for a ranged attack.

```xml
  <RectAnimation 
    frame_count="10" 
    frame_height="25" 
    frame_wait="0.07" 
    frame_width="19" 
    frames_per_row="10" 
    loop="0" 
    name="attack_ranged" 
    pos_x="0" 
    pos_y="101" 
    shrink_by_one_pixel="1" >
  </RectAnimation>
```

*   **`frame_count`**: Longest animation, 10 frames.
*   **`frame_height`**: Slightly taller (25 pixels).
*   **`frame_wait`**: Faster frame rate (0.07 seconds).
*   **`frame_width`**: Slightly wider (19 pixels).
*   **`frames_per_row`**: Different layout, 10 frames per row.
*   **`loop="0"`**: This animation does not loop.
*   **`pos_y`**: Uses the lowest section of the sprite sheet (`pos_y="101"`).
*   **`shrink_by_one_pixel="1"`**: Indicates a slight visual adjustment.