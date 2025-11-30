---
title: Roboguard Big Emissive Sprite Animations
category: entities
---

# Roboguard Big Emissive Sprite Animations

This document details the sprite animations for the "roboguard_big_emissive" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

```xml
<Sprite 
  filename="data/enemies_gfx/roboguard_big_emissive.png" 
  offset_x="9" 
  offset_y="16"
  default_animation="stand" >
  <!-- Animation definitions go here -->
</Sprite>
```

### Key Attributes:

*   **`filename`**: The path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Stand Animation

The default idle animation.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="20" 
  frame_wait="0.12" 
  frame_width="24" 
  frames_per_row="6" 
  name="stand" 
  pos_x="0" 
  pos_y="1" >
</RectAnimation>
```

### Walk Animation

The animation for when the enemy is moving.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="21" 
  frame_wait="0.12" 
  frame_width="25" 
  frames_per_row="6" 
  name="walk" 
  pos_x="0" 
  pos_y="22" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Run Animation

A faster movement animation.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="21" 
  frame_wait="0.09" 
  frame_width="25" 
  frames_per_row="8" 
  name="run" 
  pos_x="0" 
  pos_y="22" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Burn Animation

Visual effect for when the enemy is on fire.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="21" 
  frame_wait="0.09" 
  frame_width="25" 
  frames_per_row="8" 
  name="burn" 
  pos_x="0" 
  pos_y="22" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Jump Up Animation

The animation for the upward phase of a jump.

```xml
<RectAnimation 
  frame_count="1" 
  frame_height="20" 
  frame_wait="0.082" 
  frame_width="24" 
  frames_per_row="8" 
  loop="0" 
  name="jump_up" 
  pos_x="0" 
  pos_y="43" >
</RectAnimation>
```

### Jump Fall Animation

The animation for the downward phase of a jump.

```xml
<RectAnimation 
  frame_count="1" 
  frame_height="20" 
  frame_wait="0.082" 
  frame_width="24" 
  frames_per_row="8" 
  loop="0" 
  name="jump_fall" 
  pos_x="0" 
  pos_y="64" >
</RectAnimation>
```

### Attack Animation

The animation for a melee attack.

```xml
<RectAnimation 
  frame_count="5" 
  frame_height="21" 
  frame_wait="0.08" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="attack" 
  pos_x="0" 
  pos_y="85" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Attack Ranged Animation

The animation for a ranged attack.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="21" 
  frame_wait="0.08" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="attack_ranged" 
  pos_x="0" 
  pos_y="106" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Land Animation

The animation played upon landing after a jump.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="21" 
  frame_wait="0.1" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="land" 
  pos_x="0" 
  pos_y="127" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Hurt Animation

The animation played when the enemy takes damage.

```xml
<RectAnimation 
  frame_count="2" 
  frame_height="21" 
  frame_wait="0.11" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="hurt" 
  pos_x="0" 
  pos_y="148" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

## Key Animation Attributes:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack"). Crucial for triggering animations via scripts.
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are laid out horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
*   **`pos_x`**, **`pos_y`**: The starting X and Y coordinates of the animation's frames within the sprite sheet.
*   **`loop`**: If set to "0", the animation plays only once. Otherwise, it loops.
*   **`shrink_by_one_pixel`**: A flag that can slightly adjust the sprite's bounding box.