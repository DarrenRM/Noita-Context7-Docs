---
title: Slime Shooter Sprite Animations
category: enemies_gfx
---

# Slime Shooter Sprite Animations

This document details the sprite animations for the Slime Shooter enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Slime Shooter.

```xml
<Sprite
 filename="data/enemies_gfx/slimeshooter.png"
 offset_x="8"
 offset_y="16"
 default_animation="stand" >
```

*   **filename**: Path to the sprite sheet.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's position relative to its entity.
*   **default\_animation**: The animation to play when the entity spawns.

## Animations

This section breaks down the different animations defined for the Slime Shooter.

### Stand Animation

The idle animation for the Slime Shooter.

```xml
<RectAnimation
 name="stand"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "stand"
*   **pos\_x**, **pos\_y**: Starting coordinates of the animation frames on the sprite sheet.
*   **frame\_count**: Number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: Time in seconds between frames.
*   **frames\_per\_row**: How many frames are laid out horizontally on the sprite sheet.
*   **loop**: `1` for looping, `0` for non-looping.

### Walk Animation

The animation for when the Slime Shooter is walking.

```xml
<RectAnimation
 name="walk"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "walk"
*   (Other attributes are identical to "stand" in this case, indicating a potential reuse or placeholder.)

### Run Animation

The animation for when the Slime Shooter is running.

```xml
<RectAnimation
 name="run"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "run"
*   (Attributes are identical to "walk" and "stand".)

### Burn Animation

The animation for when the Slime Shooter is burning.

```xml
<RectAnimation
 name="burn"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "burn"
*   (Attributes are identical to "walk", "stand", and "run".)

### Attack Animation

The animation for a melee attack.

```xml
<RectAnimation
 name="attack"
 pos_x="0"
 pos_y="24"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
 <Event frame="0" name="bite" probability="1" check_physics_material="0"/>
</RectAnimation>
```

*   **name**: "attack"
*   **pos\_y**: Starts at `24`, indicating a different row on the sprite sheet.
*   **frame\_wait**: Faster animation speed (`0.07` seconds).
*   **loop**: `0` (non-looping).
*   **Event**: Triggers an action (`bite`) on frame `0`.

### Attack Ranged Animation

The animation for a ranged attack (shooting slime).

```xml
<RectAnimation
 name="attack_ranged"
 pos_x="0"
 pos_y="24"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.07"
 frames_per_row="6"
 loop="0" >
 <Event frame="2" name="shoot_slime" probability="1" check_physics_material="0"/>
 <Event frame="0" name="voc_shoot"/>
</RectAnimation>
```

*   **name**: "attack\_ranged"
*   **pos\_y**: Starts at `24`.
*   **frame\_wait**: Faster animation speed (`0.07` seconds).
*   **loop**: `0` (non-looping).
*   **Event**:
    *   Triggers `shoot_slime` on frame `2`.
    *   Triggers `voc_shoot` on frame `0`.

### Fly Idle Animation

The idle animation when flying.

```xml
<RectAnimation
 name="fly_idle"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "fly\_idle"
*   (Attributes are identical to "stand".)

### Fly Move Animation

The animation for movement while flying.

```xml
<RectAnimation
 name="fly_move"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="24"
 frame_wait="0.23"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **name**: "fly\_move"
*   (Attributes are identical to "stand" and "fly\_idle".)