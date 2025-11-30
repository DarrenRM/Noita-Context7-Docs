---
title: Slimeshooter Boss Limb Sprite Animations
category: entities
---

# Slimeshooter Boss Limb Sprite Animations

This document details the sprite animations for the Slimeshooter Boss Limb entity in Noita.

## Sprite Definition

The primary sprite for this entity is defined by the `<Sprite>` tag.

```xml
<Sprite
 filename="data/entities/animals/boss_limbs/slimeshooter_boss.png" 
 offset_x="8"
 offset_y="16" >
 <!-- Animation definitions go here -->
</Sprite>
```

*   **`filename`**: Specifies the path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: These attributes define the pivot point or center of the sprite relative to its entity's origin.

## Animation Definitions

The entity utilizes several `RectAnimation` tags to define different states and actions.

### Stand Animation

This animation defines the idle or standing pose of the boss limb.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "stand"
*   **`pos_x`**, **`pos_y`**: The starting coordinates on the sprite sheet for this animation.
*   **`frame_count`**: The total number of frames in this animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are present horizontally on the sprite sheet.
*   **`loop`**: `1` indicates the animation will loop continuously.

### Walk Animation

Defines the sprite frames for the entity's walking movement.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "walk"
*   **`frame_wait`**: `0.23` seconds per frame.
*   **`loop`**: `1` (loops).

### Run Animation

This animation is a copy of the "walk" animation, suggesting it uses the same visual frames for running.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "run"
*   **`frame_wait`**: `0.23` seconds per frame.
*   **`loop`**: `1` (loops).

### Burn Animation

Similar to "walk" and "run", this animation is also a copy, indicating the same visual frames are used when the entity is burning.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`name`**: "burn"
*   **`frame_wait`**: `0.23` seconds per frame.
*   **`loop`**: `1` (loops).

### Attack Animation

Defines the sprite frames for the entity's melee attack.

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="16"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
</RectAnimation>
```

*   **`name`**: "attack"
*   **`pos_x`**, **`pos_y`**: Starts at `(0, 16)` on the sprite sheet.
*   **`frame_wait`**: `0.07` seconds per frame, indicating a faster animation.
*   **`loop`**: `0` indicates this animation plays only once.

### Attack Ranged Animation

Defines the sprite frames for the entity's ranged attack. This animation shares the same sprite sheet coordinates and timing as the melee attack.

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="16"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
</RectAnimation>
```

*   **`name`**: "attack_ranged"
*   **`pos_x`**, **`pos_y`**: Starts at `(0, 16)` on the sprite sheet.
*   **`frame_wait`**: `0.07` seconds per frame.
*   **`loop`**: `0` indicates this animation plays only once.