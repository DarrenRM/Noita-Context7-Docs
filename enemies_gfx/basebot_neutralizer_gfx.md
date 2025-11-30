---
title: Basebot Neutralizer GFX
category: data/enemies_gfx
---

# Basebot Neutralizer GFX

This document details the graphical assets for the Basebot Neutralizer enemy in Noita, focusing on its sprite sheet and animation definitions.

## Sprite Definition

The main sprite definition for the Basebot Neutralizer.

### Key Attributes

*   **filename**: `data/enemies_gfx/basebot_neutralizer.png` - The path to the sprite sheet image.
*   **offset\_x**: `9` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default.

## Animations

The Basebot Neutralizer utilizes several `RectAnimation` elements to define its various visual states.

### Animation Details

| Name          | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Loop | Notes                               |
| :------------ | :---------- | :---------- | :----------- | :--------- | :------------- | :--- | :---------------------------------- |
| `stand`       | 6           | 20          | 20           | 0.12       | 8              | 1    | Default standing animation.         |
| `walk`        | 4           | 20          | 20           | 0.09       | 8              | 1    | Walking animation.                  |
| `run`         | 4           | 20          | 20           | 0.09       | 8              | 1    | Copied from `walk`.                 |
| `burn`        | 4           | 20          | 20           | 0.09       | 8              | 1    | Copied from `walk`.                 |
| `attack`      | 5           | 20          | 20           | 0.05       | 8              | 0    | Attack animation.                   |
| `attack_ranged` | 5           | 20          | 20           | 0.05       | 8              | 0    | Ranged attack animation.            |
| `fly_idle`    | 6           | 20          | 20           | 0.085      | 8              | 1    | Flying idle animation.              |
| `fly_move`    | 4           | 20          | 20           | 0.07       | 8              | 1    | Flying movement animation.          |

### Animation Frame Layout

The sprite sheet is organized with animations starting at different Y-coordinates:

*   `stand` and `fly_idle`: `pos_y="0"`
*   `walk`, `run`, `burn`, `fly_move`: `pos_y="20"`
*   `attack` and `attack_ranged`: `pos_y="40"`

### Animation Events

*   **`attack` / `attack_ranged`**:
    *   **Event**: `shoot_bullet`
    *   **Frame**: `3`
    *   **Probability**: `1`
    *   **Check Physics Material**: `0`
    *   This event triggers the firing of a projectile during the attack animations.

```xml
<Sprite
 filename="data/enemies_gfx/basebot_neutralizer.png"
 offset_x="9"
 offset_y="15"
  default_animation="stand" >

 <!-- stand -->
 <RectAnimation
  name="stand"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="20"
  frame_height="20"
  frame_wait="0.12"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>

 <!-- walk -->
 <RectAnimation
  name="walk"
  pos_x="0"
  pos_y="20"
  frame_count="4"
  frame_width="20"
  frame_height="20"
  frame_wait="0.09"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>

 <!-- fake run (just a copypaste of walk) -->
 <RectAnimation
  name="run"
  pos_x="0"
  pos_y="20"
  frame_count="4"
  frame_width="20"
  frame_height="20"
  frame_wait="0.09"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>

 <!-- fake burn (just a copypaste of walk) -->
 <RectAnimation
  name="burn"
  pos_x="0"
  pos_y="20"
  frame_count="4"
  frame_width="20"
  frame_height="20"
  frame_wait="0.09"
  frames_per_row="8"
  loop="1"   >
 </RectAnimation>

 <RectAnimation
  name="attack"
  pos_x="0"
  pos_y="40"
  frame_count="5"
  frame_width="20"
  frame_height="20"
  frame_wait="0.05"
  frames_per_row="8"
  loop="0"  >
  <Event frame="3" name="shoot_bullet" probability="1" check_physics_material="0"/>
 </RectAnimation>
 
 <RectAnimation
  name="attack_ranged"
  pos_x="0"
  pos_y="40"
  frame_count="5"
  frame_width="20"
  frame_height="20"
  frame_wait="0.05"
  frames_per_row="8"
  loop="0"  >
  <Event frame="3" name="shoot_bullet" probability="1" check_physics_material="0"/>
 </RectAnimation>
 
 <RectAnimation
  name="fly_idle"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="20"
  frame_height="20"
  frame_wait="0.085"
  frames_per_row="8"
  loop="1"  >
 </RectAnimation>
 
 <RectAnimation
  name="fly_move"
  pos_x="0"
  pos_y="20"
  frame_count="4"
  frame_width="20"
  frame_height="20"
  frame_wait="0.07"
  frames_per_row="8"
  loop="1"  >
 </RectAnimation>
</Sprite>
```