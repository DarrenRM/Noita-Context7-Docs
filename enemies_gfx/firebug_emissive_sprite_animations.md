---
title: Firebug Emissive Sprite Animations
category: data
---

# Firebug Emissive Sprite Animations

This document details the sprite animations for the Firebug enemy, specifically focusing on its emissive graphics. This file defines the visual frames and timing for various actions.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

```xml
<Sprite
 filename="data/enemies_gfx/firebug_emissive.png"
 offset_x="8"
 offset_y="13"
 default_animation="stand"
 >
```

### Key Attributes:

*   **`filename`**: The path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjustments to the sprite's position relative to its origin.
*   **`default_animation`**: The animation that plays when the sprite is first loaded or in a default state.

## Animation Definitions

The `<RectAnimation>` tags define individual animations. Each animation uses a portion of the sprite sheet.

### Stand Animation

The default animation for the Firebug.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="10"
 frame_width="16"
 frame_height="16"
 frame_wait="0.05"
 frames_per_row="10"
 loop="1"
>
</RectAnimation>
```

### Walk Animation

Used when the Firebug is moving.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="10"
 frame_width="16"
 frame_height="16"
 frame_wait="0.05"
 frames_per_row="10"
 loop="1"
>
</RectAnimation>
```

### Run Animation

Similar to walk, likely for faster movement.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="10"
 frame_width="16"
 frame_height="16"
 frame_wait="0.05"
 frames_per_row="10"
 loop="1"
>
</RectAnimation>
```

### Burn Animation

Visual representation when the Firebug is burning.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="10"
 frame_width="16"
 frame_height="16"
 frame_wait="0.05"
 frames_per_row="10"
 loop="1"
>
</RectAnimation>
```

### Flight Animations

These animations are used when the Firebug is airborne.

#### Fly Move

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="16"
 frame_count="8"
 frame_width="16"
 frame_height="16"
 frame_wait="0.035"
 frames_per_row="8"
 loop="1"
>
</RectAnimation>
```

#### Fly Idle

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="16"
 frame_count="8"
 frame_width="16"
 frame_height="16"
 frame_wait="0.035"
 frames_per_row="8"
 loop="1"
>
</RectAnimation>
```

### Attack Animations

Animations for the Firebug's offensive actions.

#### Dash Attack

```xml
<RectAnimation
 name="attack_dash"
 pos_x="0"
 pos_y="16"
 frame_count="8"
 frame_width="16"
 frame_height="16"
 frame_wait="0.035"
 frames_per_row="8"
 loop="1"
>
</RectAnimation>
```

#### Ranged Attack

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="32"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.06"
 frames_per_row="8"
 loop="0"
>
</RectAnimation>
```

### Key Animation Attributes:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk").
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation frames within the sprite sheet.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are laid out horizontally on the sprite sheet.
*   **`loop`**: `1` for looping animations, `0` for one-time animations.