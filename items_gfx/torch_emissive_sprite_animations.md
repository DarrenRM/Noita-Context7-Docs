---
title: Torch Emissive Sprite Animations
category: items_gfx
---

# Torch Emissive Sprite Animations

This document details the sprite animations for the `torch_emissive` item in Noita, focusing on its visual representation and animation properties.

## Sprite Definition

The primary sprite definition for the torch is as follows:

```xml
<Sprite
 filename="data/items_gfx/torch_emissive.png"
 offset_x="16.5"
 offset_y="20.0"
 default_animation="default" >
</Sprite>
```

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
*   **`offset_x`**, **`offset_y`**: Define the sprite's pivot point relative to its center.
*   **`default_animation`**: Sets the animation to play by default when the sprite is active.

## Animation Details

The `torch_emissive` sprite utilizes several `RectAnimation` elements to define different visual states and their transitions.

### `default` Animation

This is the primary animation for the torch, likely representing its active, lit state.

```xml
<RectAnimation
 name="default"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="32"
 frame_height="32"
 frame_wait="0.09"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

#### Key Attributes:

*   **`name`**: "default" - Identifies this animation.
*   **`pos_x`**, **`pos_y`**: "0", "0" - The starting position of the animation frames within the sprite sheet.
*   **`frame_count`**: "4" - The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: "32", "32" - The dimensions of each individual frame.
*   **`frame_wait`**: "0.09" - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: "4" - How many frames are arranged horizontally in the sprite sheet for this animation.
*   **`loop`**: "1" - Indicates that this animation will loop indefinitely.

### `appear` Animation

This animation likely plays when the torch is first spawned or becomes active.

```xml
<RectAnimation
 name="appear"
 pos_x="0"
 pos_y="32"
 frame_count="5"
 frame_width="32"
 frame_height="32"
 frame_wait="0.05"
 frames_per_row="5"
 loop="0" >
</RectAnimation>
```

#### Key Attributes:

*   **`name`**: "appear" - Identifies this animation.
*   **`pos_y`**: "32" - The starting Y-coordinate for these frames in the sprite sheet.
*   **`frame_count`**: "5" - The total number of frames.
*   **`frame_wait`**: "0.05" - A faster frame wait, suggesting a quick visual effect.
*   **`frames_per_row`**: "5" - Frames are arranged horizontally.
*   **`loop`**: "0" - This animation plays only once.

### `out` Animation

This animation might represent the torch's flame dying out or being extinguished.

```xml
<RectAnimation
 name="out"
 pos_x="0"
 pos_y="96"
 frame_count="0"
 frame_width="32"
 frame_height="32"
 frame_wait="0.09"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

#### Key Attributes:

*   **`name`**: "out" - Identifies this animation.
*   **`pos_y`**: "96" - The starting Y-coordinate for these frames.
*   **`frame_count`**: "0" - **Note:** A `frame_count` of "0" for an animation named "out" is unusual. This might indicate that this animation is intended to be a placeholder or is handled by other game logic, or it might be an error in the original file. Typically, a `frame_count` of 0 would mean no frames are displayed.
*   **`loop`**: "1" - Intended to loop, though with 0 frames, its effect is unclear without further context.

### `disappear` Animation

This animation likely plays when the torch is removed or destroyed.

```xml
<RectAnimation
 name="disappear"
 pos_x="0"
 pos_y="64"
 frame_count="3"
 frame_width="32"
 frame_height="32"
 frame_wait="0.05"
 frames_per_row="3"
 loop="0" >
</RectAnimation>
```

#### Key Attributes:

*   **`name`**: "disappear" - Identifies this animation.
*   **`pos_y`**: "64" - The starting Y-coordinate for these frames.
*   **`frame_count`**: "3" - The total number of frames.
*   **`frame_wait`**: "0.05" - A quick animation for removal.
*   **`frames_per_row`**: "3" - Frames are arranged horizontally.
*   **`loop`**: "0" - This animation plays only once.