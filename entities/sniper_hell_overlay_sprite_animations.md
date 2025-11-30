---
title: Sniper Hell Overlay Sprite Animations
category: entities
---

# Sniper Hell Overlay Sprite Animations

This document details the sprite animations for the "Sniper Hell Overlay" entity in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its offsets.

```xml
<Sprite 
  filename="data/enemies_gfx/sniper_hell_overlay.png" 
  offset_x="5" 
  offset_y="14"
  default_animation="stand" >
  <!-- Animation definitions follow -->
</Sprite>
```

*   **`filename`**: Path to the sprite sheet image.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's position relative to its origin.
*   **`default_animation`**: The animation to play when the entity spawns or has no other animation specified.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack_ranged").
*   **`frame_count`**: Total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed.
*   **`pos_x`**, **`pos_y`**: The starting coordinates of the animation frames on the sprite sheet.
*   **`loop`**: If "0", the animation plays once; otherwise, it loops.
*   **`shrink_by_one_pixel`**: A visual adjustment, often used for smoother transitions.

### Notable Animations and Events:

#### `stand` Animation

*   **Description**: The default idle animation.
*   **Frames**: 12 frames, 20x17 pixels each.
*   **Frame Wait**: 0.15 seconds.
*   **Events**:
    *   `breath` (on frame 8): Triggers a "breath" action.

```xml
  <RectAnimation 
    frame_count="12" 
    frame_height="17" 
    frame_wait="0.15" 
    frame_width="20" 
    frames_per_row="12" 
    name="stand" 
    pos_x="0" 
    pos_y="1" >
    <Event 
      check_physics_material="0" 
      frame="8" 
      max_distance="500" 
      name="breath" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

#### `walk` Animation

*   **Description**: Animation for walking.
*   **Frames**: 6 frames, 21x18 pixels each.
*   **Frame Wait**: 0.06 seconds.
*   **Events**:
    *   `step` (on frame 0 and 3): Triggers a "step" sound/effect.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.06" 
    frame_width="21" 
    frames_per_row="6" 
    name="walk" 
    pos_x="0" 
    pos_y="19" 
    shrink_by_one_pixel="1" >
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
```

#### `run` Animation

*   **Description**: Animation for running.
*   **Frames**: 6 frames, 21x18 pixels each.
*   **Frame Wait**: 0.05 seconds.
*   **Events**:
    *   `step` (on frame 0 and 3): Triggers a "step" sound/effect.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    name="run" 
    pos_x="0" 
    pos_y="19" 
    shrink_by_one_pixel="1" >
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
```

#### `attack_ranged` Animation

*   **Description**: Animation for ranged attacks.
*   **Frames**: 13 frames, 21x18 pixels each.
*   **Frame Wait**: 0.07 seconds.
*   **Loop**: Disabled (plays once).
*   **Events**:
    *   `shoot_sniper` (on frame 8): Triggers the sniper shot.

```xml
  <RectAnimation 
    frame_count="13" 
    frame_height="18" 
    frame_wait="0.07" 
    frame_width="21" 
    frames_per_row="13" 
    loop="0" 
    name="attack_ranged" 
    pos_x="0" 
    pos_y="37" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="8" 
      max_distance="500" 
      name="shoot_sniper" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

#### `attack` Animation

*   **Description**: General attack animation (likely melee).
*   **Frames**: 6 frames, 21x18 pixels each.
*   **Frame Wait**: 0.05 seconds.
*   **Loop**: Disabled.
*   **Events**:
    *   `kick` (on frame 3): Triggers a "kick" action.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="6" 
    loop="0" 
    name="attack" 
    pos_x="0" 
    pos_y="55" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="3" 
      max_distance="500" 
      name="kick" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

#### `burn` Animation

*   **Description**: Animation when the entity is burning.
*   **Frames**: 6 frames, 21x18 pixels each.
*   **Frame Wait**: 0.04 seconds.
*   **Events**:
    *   `step` (on frame 0 and 3): Triggers a "step" sound/effect, possibly indicating movement while burning.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.04" 
    frame_width="21" 
    frames_per_row="8" 
    name="burn" 
    pos_x="0" 
    pos_y="73" 
    shrink_by_one_pixel="1" >
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
```

#### `jump_up` and `jump_fall` Animations

*   **Description**: Animations for jumping.
*   **Frames**: 3 frames each, 21x18 pixels.
*   **Frame Wait**: 0.05 seconds.
*   **Loop**: Disabled.
*   **Events**:
    *   `jump_up`: Contains a `jump` event on frame 0.
    *   `jump_fall`: No specific events defined within this animation.

```xml
  <RectAnimation 
    frame_count="3" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    loop="0" 
    name="jump_up" 
    pos_x="0" 
    pos_y="91" 
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
  <RectAnimation 
    frame_count="3" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    loop="0" 
    name="jump_fall" 
    pos_x="0" 
    pos_y="109" 
    shrink_by_one_pixel="1" >
  </RectAnimation>
```

#### `swim_idle` and `swim_move` Animations

*   **Description**: Animations for swimming.
*   **Frames**: 6 frames each, 21x18 pixels.
*   **Frame Wait**: 0.05 seconds.
*   **Events**:
    *   `paddle` (on frame 0 and 3): Triggers a "paddle" action.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    name="swim_idle" 
    pos_x="0" 
    pos_y="127" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="0" 
      max_distance="500" 
      name="paddle" 
      on_finished="0" 
      probability="1" >
    </Event>
    <Event 
      check_physics_material="0" 
      frame="3" 
      max_distance="500" 
      name="paddle" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    name="swim_move" 
    pos_x="0" 
    pos_y="127" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="0" 
      max_distance="500" 
      name="paddle" 
      on_finished="0" 
      probability="1" >
    </Event>
    <Event 
      check_physics_material="0" 
      frame="3" 
      max_distance="500" 
      name="paddle" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

#### `attack_throw` Animation

*   **Description**: Animation for throwing an item.
*   **Frames**: 6 frames, 21x18 pixels each.
*   **Frame Wait**: 0.05 seconds.
*   **Loop**: Disabled.
*   **Events**:
    *   `throw` (on frame 4): Triggers the throwing action.

```xml
  <RectAnimation 
    frame_count="6" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="8" 
    loop="0" 
    name="attack_throw" 
    pos_x="0" 
    pos_y="145" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="4" 
      max_distance="500" 
      name="throw" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

#### `jump_prepare` Animation

*   **Description**: Animation for preparing to jump.
*   **Frames**: 3 frames, 21x18 pixels each.
*   **Frame Wait**: 0.05 seconds.
*   **Loop**: Disabled.
*   **Events**:
    *   `jump_start` (on frame 3): Triggers the start of the jump.

```xml
  <RectAnimation 
    frame_count="3" 
    frame_height="18" 
    frame_wait="0.05" 
    frame_width="21" 
    frames_per_row="13" 
    loop="0" 
    name="jump_prepare" 
    pos_x="0" 
    pos_y="163" 
    shrink_by_one_pixel="1" >
    <Event 
      check_physics_material="0" 
      frame="3" 
      max_distance="500" 
      name="jump_start" 
      on_finished="0" 
      probability="1" >
    </Event>
  </RectAnimation>
```

### Key Event Attributes:

*   **`name`**: The identifier of the event (e.g., "shoot_sniper", "step", "kick"). This is crucial for triggering specific game logic.
*   **`frame`**: The specific frame number within the animation where the event occurs.
*   **`probability`**: The chance (0-1) that the event will trigger.
*   **`check_physics_material`**: If "1", the event might be influenced by the physics material of the ground.
*   **`max_distance`**: The maximum distance at which the event can be triggered.
*   **`on_finished`**: If "1", the event triggers when the animation finishes.