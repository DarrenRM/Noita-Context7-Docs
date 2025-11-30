---
title: Wizard Twitchy Sprite Definitions
category: data/enemies_gfx
---

# Wizard Twitchy Sprite Definitions

This document details the sprite and animation definitions for the "wizard_twitchy" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the core visual properties and links to the sprite sheet and hotspot data.

### Key Attributes:

*   **filename**: `data/enemies_gfx/wizard_twitchy.png` - Path to the sprite sheet image.
*   **hotspots_filename**: `data/enemies_gfx/wizard_hotspots.png` - Path to the image defining collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the wizard. Each animation consists of a sequence of frames from the sprite sheet.

### Common Attributes for `<RectAnimation>`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: Total number of frames in the animation.
*   **frame\_width**: Width of a single frame in pixels.
*   **frame\_height**: Height of a single frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: Delay between frames in seconds.
*   **pos\_x**: X-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **pos\_y**: Y-coordinate of the top-left corner of the animation block on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop (default is `1` for looping).
*   **shrink\_by\_one\_pixel**: `1` indicates frames are slightly smaller than their defined `frame_width`/`frame_height`.

### Defined Animations:

| Animation Name   | Frame Count | Frame Size (WxH) | Frame Wait | Frames Per Row | Pos (X,Y) | Loop | Notes                               |
| :--------------- | :---------- | :--------------- | :--------- | :------------- | :-------- | :--- | :---------------------------------- |
| **stand**        | 6           | 16x19            | 0.05       | 6              | (0,1)     | 1    | Idle animation.                     |
| **walk**         | 6           | 16x19            | 0.045      | 6              | (0,21)    | 1    | Walking animation.                  |
| **run**          | 6           | 16x19            | 0.045      | 6              | (0,21)    | 1    | Running animation.                  |
| **burn**         | 6           | 16x19            | 0.045      | 6              | (0,21)    | 1    | Burning animation.                  |
| **attack\_ranged** | 7           | 17x20            | 0.04       | 6              | (0,41)    | 0    | Ranged attack. `shrink_by_one_pixel` is 1. |
| **fly\_idle**    | 4           | 17x20            | 0.06       | 15             | (0,81)    | 1    | Flying idle animation. `shrink_by_one_pixel` is 1. |
| **fly\_move**    | 4           | 17x20            | 0.06       | 15             | (0,101)   | 1    | Flying movement animation. `shrink_by_one_pixel` is 1. |

## Animation Events

Events can be triggered at specific frames within an animation.

### Key Attributes for `<Event>`:

*   **name**: The name of the event (e.g., "step", "shoot\_magic").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: The chance of the event triggering (1 is 100%).
*   **on\_finished**: `0` means the event does not stop the animation.
*   **check\_physics\_material**: `1` means the event checks the physics material of the ground.
*   **max\_distance**: Maximum distance for certain event types.

### Defined Events:

*   **walk/run/burn animations**:
    *   `name="step"`, `frame=0`, `probability=1`, `check_physics_material=1`
    *   `name="step"`, `frame=3`, `probability=1`, `check_physics_material=1`
    *   These events likely trigger footstep sounds or effects.
*   **attack\_ranged animation**:
    *   `name="shoot_magic"`, `frame=5`, `probability=1`, `check_physics_material=0`
    *   This event triggers the projectile firing action.

## Hotspots

Hotspots define specific points on the sprite for collision, interaction, or visual effects.

### Defined Hotspots:

*   **cape**:
    *   `color="ff"` (likely white or transparent, indicating a general area or no specific color mapping)
    *   This hotspot might define the area of the wizard's cape for visual effects or interactions.

```xml
<Sprite 
  filename="data/enemies_gfx/wizard_twitchy.png" 
  hotspots_filename="data/enemies_gfx/wizard_hotspots.png" 
  offset_x="8" 
  offset_y="14"
  default_animation="stand" >

  <RectAnimation 
    frame_count="6" 
    frame_height="19" 
    frame_wait="0.05" 
    frame_width="16" 
    frames_per_row="6" 
    name="stand" 
    pos_x="0" 
    pos_y="1" >
  </RectAnimation>

  <RectAnimation 
    frame_count="6" 
    frame_height="19" 
    frame_wait="0.045" 
    frame_width="16" 
    frames_per_row="6" 
    name="walk" 
    pos_x="0" 
    pos_y="21" >
    <Event 
      check_physics_material="1" 
      frame="0" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
    <Event 
      check_physics_material="1" 
      frame="3" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>

  <RectAnimation 
    frame_count="6" 
    frame_height="19" 
    frame_wait="0.045" 
    frame_width="16" 
    frames_per_row="6" 
    name="run" 
    pos_x="0" 
    pos_y="21" >
    <Event 
      check_physics_material="1" 
      frame="0" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
    <Event 
      check_physics_material="1" 
      frame="3" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>

  <RectAnimation 
    frame_count="6" 
    frame_height="19" 
    frame_wait="0.045" 
    frame_width="16" 
    frames_per_row="6" 
    name="burn" 
    pos_x="0" 
    pos_y="21" >
    <Event 
      check_physics_material="1" 
      frame="0" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
    <Event 
      check_physics_material="1" 
      frame="3" 
      max_distance="500" 
      name="step" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>

  <RectAnimation 
    frame_count="7" 
    frame_height="20" 
    frame_wait="0.04" 
    frame_width="17" 
    frames_per_row="6" 
    loop="0" 
    name="attack_ranged" 
    pos_x="0" 
    pos_y="41" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="5" 
      max_distance="500" 
      name="shoot_magic" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>

  <RectAnimation 
    frame_count="4" 
    frame_height="20" 
    frame_wait="0.06" 
    frame_width="17" 
    frames_per_row="15" 
    name="fly_idle" 
    pos_x="0" 
    pos_y="81" 
    shrink_by_one_pixel="1" >
  </RectAnimation>

  <RectAnimation 
    frame_count="4" 
    frame_height="20" 
    frame_wait="0.06" 
    frame_width="17" 
    frames_per_row="15" 
    name="fly_move" 
    pos_x="0" 
    pos_y="101" 
    shrink_by_one_pixel="1" >
  </RectAnimation>

  <Hotspot 
    color="ff" 
    name="cape" >
  </Hotspot>
</Sprite>
```