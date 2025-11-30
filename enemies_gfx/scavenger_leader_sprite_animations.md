---
title: Scavenger Leader Sprite Animations
category: data/enemies_gfx/
---

# Scavenger Leader Sprite Animations

This document details the sprite animations for the Scavenger Leader enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Scavenger Leader.

```xml
<Sprite 
  filename="data/enemies_gfx/scavenger_leader.png" 
  offset_x="12" 
  offset_y="10"
  default_animation="stand" >
  <!-- ... RectAnimation elements ... -->
</Sprite>
```

### Key Attributes:

*   **filename**: Path to the sprite sheet image.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's position relative to its entity's origin.
*   **default\_animation**: The animation to play when the entity is idle or no other animation is specified.

## RectAnimation Definitions

Each `RectAnimation` tag defines a specific animation sequence.

### Stand Animation

The default idle animation.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="25" 
  frame_wait="0.16" 
  frame_width="25" 
  frames_per_row="8" 
  name="stand" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Walk Animation

Used for general movement.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="25" 
  frame_wait="0.12" 
  frame_width="25" 
  frames_per_row="8" 
  name="walk" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <Event 
    check_physics_material="1" 
    frame="2" 
    max_distance="500" 
    name="step" 
    on_finished="0" 
    probability="1" >
  </Event>
  <Event 
    check_physics_material="1" 
    frame="5" 
    max_distance="500" 
    name="step" 
    on_finished="0" 
    probability="1" >
  </Event>
</RectAnimation>
```

### Run Animation

Similar to walk, likely for faster movement.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="25" 
  frame_wait="0.12" 
  frame_width="25" 
  frames_per_row="8" 
  name="run" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <!-- Events similar to walk -->
</RectAnimation>
```

### Burn Animation

Visuals for when the entity is on fire.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="25" 
  frame_wait="0.12" 
  frame_width="25" 
  frames_per_row="8" 
  name="burn" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <!-- Events similar to walk -->
</RectAnimation>
```

### Jump Up Animation

Animation for the upward phase of a jump.

```xml
<RectAnimation 
  frame_count="3" 
  frame_height="25" 
  frame_wait="0.082" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="jump_up" 
  pos_x="0" 
  pos_y="51" 
  shrink_by_one_pixel="1" >
  <Event 
    check_physics_material="1" 
    frame="0" 
    max_distance="500" 
    name="jump" 
    on_finished="0" 
    probability="1" >
  </Event>
</RectAnimation>
```

### Jump Fall Animation

Animation for the downward phase of a jump.

```xml
<RectAnimation 
  frame_count="2" 
  frame_height="25" 
  frame_wait="0.082" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="jump_fall" 
  pos_x="0" 
  pos_y="76" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Land Animation

Animation played upon landing.

```xml
<RectAnimation 
  frame_count="2" 
  frame_height="25" 
  frame_wait="0.074" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="land" 
  pos_x="0" 
  pos_y="101" 
  shrink_by_one_pixel="1" >
  <Event 
    check_physics_material="1" 
    frame="0" 
    max_distance="500" 
    name="land" 
    on_finished="0" 
    probability="1" >
  </Event>
</RectAnimation>
```

### Attack Animation

Animation for a melee attack.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.095" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="attack" 
  pos_x="0" 
  pos_y="126" 
  shrink_by_one_pixel="1" >
  <Event 
    check_physics_material="0" 
    frame="3" 
    max_distance="500" 
    name="hit" 
    on_finished="0" 
    probability="1" >
  </Event>
</RectAnimation>
```

### Attack Ranged Animation

Animation for a ranged attack.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="25" 
  frames_per_row="8" 
  loop="0" 
  name="attack_ranged" 
  pos_x="0" 
  pos_y="151" 
  shrink_by_one_pixel="1" >
  <Event 
    check_physics_material="0" 
    frame="3" 
    max_distance="500" 
    name="hit" 
    on_finished="0" 
    probability="1" >
  </Event>
</RectAnimation>
```

### Fly Idle Animation

Idle animation when flying.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.12" 
  frame_width="25" 
  frames_per_row="8" 
  name="fly_idle" 
  pos_x="0" 
  pos_y="176" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Fly Move Animation

Movement animation when flying.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="25" 
  frames_per_row="8" 
  name="fly_move" 
  pos_x="0" 
  pos_y="201" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

## Key `RectAnimation` Attributes

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack"). This is crucial for triggering animations via scripts.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**, **pos\_y**: The starting coordinates (top-left corner) of the animation frames within the sprite sheet.
*   **loop**: If "0", the animation plays only once; otherwise, it loops.
*   **shrink\_by\_one\_pixel**: A visual adjustment, often set to "1".

## Event Definitions

Events can be attached to specific frames within an animation to trigger actions.

### Key `Event` Attributes:

*   **name**: The type of event (e.g., "step", "jump", "land", "hit").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: The chance (0 to 1) that the event will trigger.
*   **check\_physics\_material**: If "1", the event might depend on the material the entity is standing on.
*   **max\_distance**: A parameter that might influence the event's effect.
*   **on\_finished**: If "1", the event triggers when the animation finishes; otherwise, it triggers at the specified frame.

**Note:** The `walk`, `run`, and `burn` animations share similar "step" events, suggesting they are used for ground-based movement and can trigger footstep sounds or effects. The `attack` and `attack_ranged` animations have a "hit" event on their final frame, indicating when damage or hit registration should occur.