---
title: Big Frog Sprite Animations
category: entities
---

# Big Frog Sprite Animations

This document details the sprite animations for the "Big Frog" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Big Frog.

```xml
<Sprite
 filename="data/enemies_gfx/frog_big.png"
 offset_x="8"
 offset_y="11"
 default_animation="stand" >
</Sprite>
```

*   **filename**: Path to the sprite sheet.
*   **offset_x**, **offset_y**: Adjusts the sprite's position relative to its origin.
*   **default_animation**: The animation to play when the entity is idle or spawned.

## Animations

### Stand Animation

The default idle animation for the Big Frog.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="16"
 frame_height="16"
 frame_wait="0.16"
 frames_per_row="12"
 loop="1" >
</RectAnimation>
```

*   **name**: "stand"
*   **pos_x**, **pos_y**: Starting coordinates of the animation frames on the sprite sheet.
*   **frame_count**: Number of frames in this animation.
*   **frame_width**, **frame_height**: Dimensions of each individual frame.
*   **frame_wait**: Delay between frames in seconds.
*   **frames_per_row**: How many frames are in a single row of the sprite sheet.
*   **loop**: `1` indicates the animation will loop continuously.

### Jump Up Animation

The animation played when the Big Frog initiates a jump.

```xml
<RectAnimation
 name="jump_up"
 pos_x="0"
 pos_y="16"
 frame_count="1"
 frame_width="16"
 frame_height="16"
 frame_wait="0.082"
 frames_per_row="12"
 loop="0" >
 <Event frame="0" name="jump" probability="1" check_physics_material="1"/>
</RectAnimation>
```

*   **name**: "jump_up"
*   **pos_y**: Starts on the second row of the sprite sheet (y-offset of 16).
*   **frame_count**: `1` - This is a single-frame animation.
*   **loop**: `0` indicates the animation plays once.
*   **Event**: Triggers a "jump" event on frame 0, with a probability of 1, and checks for physics material.

### Jump Falling Animation

The animation played while the Big Frog is falling after a jump.

```xml
<RectAnimation
 name="jump_fall"
 pos_x="0"
 pos_y="32"
 frame_count="1"
 frame_width="16"
 frame_height="16"
 frame_wait="0.082"
 frames_per_row="12"
 loop="0" >
</RectAnimation>
```

*   **name**: "jump_fall"
*   **pos_y**: Starts on the third row of the sprite sheet (y-offset of 32).
*   **frame_count**: `1` - This is a single-frame animation.
*   **loop**: `0` indicates the animation plays once.

### Attack Ranged Animation

The animation for the Big Frog's ranged attack.

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="48"
 frame_count="12"
 frame_width="16"
 frame_height="16"
 frame_wait="0.07"
 frames_per_row="12"
 loop="1" >
</RectAnimation>
```

*   **name**: "attack_ranged"
*   **pos_y**: Starts on the fourth row of the sprite sheet (y-offset of 48).
*   **frame_count**: `12` - This animation consists of 12 frames.
*   **frame_wait**: A faster frame delay for an active attack.
*   **loop**: `1` indicates the animation will loop.