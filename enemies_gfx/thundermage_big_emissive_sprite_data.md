---
title: Thundermage Big Emissive Sprite Data
category: enemies_gfx
---

# Thundermage Big Emissive Sprite Data

This document details the sprite data for the "Thundermage Big Emissive" enemy in Noita, focusing on its graphical animations and associated events.

## Sprite Definition

The main `<Sprite>` tag defines the overall sprite properties and references the primary image file.

```xml
<Sprite 
  default_animation="stand" 
  filename="data/enemies_gfx/thundermage_big_emissive.png" 
  offset_x="14" 
  offset_y="30" >
  <!-- Animation definitions go here -->
</Sprite>
```

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default when the sprite is loaded. Here, it's set to "stand".
*   **`filename`**: The path to the sprite sheet image file.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.

## Animation Definitions (`RectAnimation`)

The `<Sprite>` tag contains multiple `<RectAnimation>` elements, each defining a distinct animation sequence.

### Common Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame in pixels.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**, **`pos_y`**: The starting coordinates (top-left corner) of the animation frames within the sprite sheet.
*   **`loop`**: If set to "0", the animation plays only once; otherwise, it loops.
*   **`shrink_by_one_pixel`**: A value indicating if frames should be shrunk by one pixel, often used for subtle visual effects.

### Notable Animations and Events:

#### `stand` Animation

*   **`frame_count`**: 6
*   **`frame_height`**: 34
*   **`frame_width`**: 28
*   **`frame_wait`**: 0.07
*   **`frames_per_row`**: 8
*   **`pos_y`**: 1

#### `walk` Animation

*   **`frame_count`**: 6
*   **`frame_height`**: 35
*   **`frame_width`**: 29
*   **`frame_wait`**: 0.07
*   **`frames_per_row`**: 8
*   **`pos_y`**: 36
*   **`shrink_by_one_pixel`**: 1

##### Events within `walk`:

*   **`step`**: Triggered at frames 2 and 5. `check_physics_material="1"` suggests it might interact with or react to the environment's physics.

#### `run` Animation

*   Similar properties to `walk`, with `frame_wait` at 0.07.
*   Also includes `step` events at frames 2 and 5.

#### `burn` Animation

*   Similar properties to `walk` and `run`.
*   Also includes `step` events at frames 2 and 5.

#### `fly_idle` Animation

*   **`frame_count`**: 4
*   **`frame_height`**: 35
*   **`frame_width`**: 29
*   **`frame_wait`**: 0.09
*   **`frames_per_row`**: 8
*   **`pos_y`**: 71

#### `fly_move` Animation

*   **`frame_count`**: 4
*   **`frame_height`**: 34
*   **`frame_width`**: 28
*   **`frame_wait`**: 0.09
*   **`frames_per_row`**: 8
*   **`pos_y`**: 106

#### `attack` Animation

*   **`frame_count`**: 8
*   **`frame_height`**: 35
*   **`frame_width`**: 29
*   **`frame_wait`**: 0.09
*   **`frames_per_row`**: 8
*   **`loop`**: 0 (plays once)
*   **`pos_y`**: 141
*   **`shrink_by_one_pixel`**: 1

##### Events within `attack`:

*   **`shoot_thunder`**: Triggered at frame 4. `check_physics_material="0"` indicates this event is not directly tied to physics material checks.

#### `attack_ranged` Animation

*   **`frame_count`**: 8
*   **`frame_height`**: 35
*   **`frame_width`**: 29
*   **`frame_wait`**: 0.07
*   **`frames_per_row`**: 10
*   **`loop`**: 0 (plays once)
*   **`pos_y`**: 141
*   **`shrink_by_one_pixel`**: 1

##### Events within `attack_ranged`:

*   **`shoot_thunder`**: Triggered at frame 4. Similar to the `attack` event, `check_physics_material="0"`.

---