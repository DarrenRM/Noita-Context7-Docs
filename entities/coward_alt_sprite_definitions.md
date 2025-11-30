---
title: Coward Alt Sprite Definitions
category: entities
---

# Coward Alt Sprite Definitions

This document details the sprite definitions for the "coward_alt" enemy in Noita, focusing on its visual animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base sprite and its default animation.

### Key Attributes:

*   **filename**: Specifies the base image file used for the sprite.
*   **offset\_x**: Horizontal offset for the sprite's origin.
*   **offset\_y**: Vertical offset for the sprite's origin.
*   **default\_animation**: The animation to play by default.

```xml
<Sprite
 filename="data/items_gfx/normals_orb_base"
 offset_x="8"
 offset_y="18"
 default_animation="stand" >
 <!-- ... animations ... -->
</Sprite>
```

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the enemy.

### Key Attributes for `RectAnimation`:

*   **name**: The name of the animation (e.g., "stand", "walk", "attack").
*   **pos\_x**: X-coordinate of the top-left corner of the animation frames within the `filename`.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation frames within the `filename`.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for yes, 0 for no).

### Animation Details:

#### `stand` Animation

*   **Description**: The default idle animation.
*   **Frames**: 4 frames.
*   **Frame Size**: 20x20 pixels.
*   **Frame Delay**: 0.2 seconds per frame.
*   **Looping**: Yes.

```xml
<!-- stand -->
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.2"
 frames_per_row="7"
 loop="1" >
</RectAnimation>
```

#### `walk` Animation

*   **Description**: Animation for walking.
*   **Frames**: 4 frames.
*   **Frame Size**: 20x20 pixels.
*   **Frame Delay**: 0.2 seconds per frame.
*   **Looping**: Yes.

```xml
<!-- walk -->
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.2"
 frames_per_row="7"
 loop="1" >
</RectAnimation>
```

#### `run` Animation

*   **Description**: Animation for running (copied from `walk`).
*   **Frames**: 4 frames.
*   **Frame Size**: 20x20 pixels.
*   **Frame Delay**: 0.2 seconds per frame.
*   **Looping**: Yes.

```xml
<!-- run - copied from walk -->
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.2"
 frames_per_row="7"
 loop="1" >
</RectAnimation>
```

#### `burn` Animation

*   **Description**: Animation for being burned (copied from `walk`).
*   **Frames**: 4 frames.
*   **Frame Size**: 20x20 pixels.
*   **Frame Delay**: 0.2 seconds per frame.
*   **Looping**: Yes.

```xml
<!-- burn - copied from walk -->
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="20"
 frame_height="20"
 frame_wait="0.2"
 frames_per_row="7"
 loop="1" >
</RectAnimation>
```

#### `attack` Animation

*   **Description**: Animation for attacking.
*   **Frames**: 7 frames.
*   **Frame Size**: 20x20 pixels.
*   **Frame Delay**: 0.07 seconds per frame.
*   **Looping**: No.

##### Attack Event

*   **Description**: An event triggered during the attack animation.
*   **Trigger Frame**: Frame 5.
*   **Event Name**: `attack_bite`.
*   **Max Distance**: 500.

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="20"
 frame_count="7"
 frame_width="20"
 frame_height="20"
 frame_wait="0.07"
 frames_per_row="7"
 loop="0" >
 <Event
  check_physics_material="0"
  frame="5"
  max_distance="500"
  name="attack_bite"
  on_finished="0"
  probability="1" >
 </Event>
</RectAnimation>
```