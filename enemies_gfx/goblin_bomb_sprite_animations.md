---
title: Goblin Bomb Sprite Animations
category: data/enemies_gfx/
---

# Goblin Bomb Sprite Animations

This document details the sprite animations for the Goblin Bomb enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Goblin Bomb.

```xml
<Sprite
 filename="data/enemies_gfx/goblin_bomb.png"
 offset_x="8"
 offset_y="20"
 default_animation="stand" >
```

### Key Attributes:

*   **filename**: The path to the sprite sheet image.
*   **offset\_x, offset\_y**: Adjustments to the sprite's position relative to its entity.
*   **default\_animation**: The animation to play when the entity is idle or no other animation is specified.

## Hotspots

Defines specific points on the sprite, often used for interaction or animation events.

```xml
  <Hotspot
    color="00ff0000"
    name="hand" >
  </Hotspot>

  <Hotspot
    color="000000ff"
    name="eye" >
  </Hotspot>
```

### Key Attributes:

*   **name**: Identifies the hotspot (e.g., "hand", "eye").
*   **color**: RGBA color value. The alpha channel (last two hex digits) often indicates visibility or purpose.

## Animations

Each `RectAnimation` tag defines a distinct animation sequence.

### Stand Animation

The default idle animation.

```xml
 <!-- stand -->
 <RectAnimation
  name="stand"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="16"
  frame_height="24"
  frame_wait="0.2"
  frames_per_row="12"
  loop="1" >
 </RectAnimation>
```

### Walk Animation

Used for movement.

```xml
 <!-- walk -->
 <RectAnimation
  name="walk"
  pos_x="0"
  pos_y="24"
  frame_count="6"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="1" >
  <Event frame="0" name="step" probability="1" check_physics_material="1"/>
  <Event frame="2" name="step" probability="1" check_physics_material="1"/>
 </RectAnimation>
```

*   **Events**: Includes "step" events on specific frames, potentially triggering sound effects or other game logic. `check_physics_material="1"` suggests it reacts to the ground.

### Jump Animations

A sequence for jumping.

```xml
 <!-- jump_prepare -->
 <RectAnimation
  name="jump_prepare"
  pos_x="0"
  pos_y="48"
  frame_count="3"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="0" >
  <Event frame="2" name="jump_start"/>
 </RectAnimation>

 <!-- jump_up -->
 <RectAnimation
  name="jump_up"
  pos_x="0"
  pos_y="72"
  frame_count="1"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="0" >
  <Event frame="0" name="jump" probability="1" check_physics_material="1"/>
 </RectAnimation>

<!-- jump_fall -->
 <RectAnimation
  name="jump_fall"
  pos_x="0"
  pos_y="96"
  frame_count="3"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="1" >
 </RectAnimation>

 <!-- land -->
 <RectAnimation
  name="land"
  pos_x="0"
  pos_y="120"
  frame_count="3"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="0" >
 </RectAnimation>
```

*   **Events**: `jump_start` and `jump` events are crucial for AI controlling jump actions.

### Attack Animations

Animations related to attacking.

```xml
 <!-- attack_ranged -->
 <RectAnimation
  name="attack_ranged"
  pos_x="0"
  pos_y="144"
  frame_count="11"
  frame_width="16"
  frame_height="24"
  frame_wait="0.12"
  frames_per_row="12"
  loop="0" >
  <Event frame="6" name="throw" probability="1" check_physics_material="0"/>
 </RectAnimation>

 <RectAnimation
  name="throw"
  pos_x="0"
  pos_y="144"
  frame_count="11"
  frame_width="16"
  frame_height="24"
  frame_wait="0.12"
  frames_per_row="12"
  loop="0" >
  <Event frame="6" name="throw_release" probability="1"/>
 </RectAnimation>

 <RectAnimation
  name="attack"
  pos_x="0"
  pos_y="168"
  frame_count="3"
  frame_width="16"
  frame_height="24"
  frame_wait="0.12"
  frames_per_row="12"
  loop="0" >
  <Event frame="2" name="hit" probability="1" check_physics_material="0"/>
 </RectAnimation>
```

*   **Events**: `throw` and `hit` events are key for AI to trigger attacks. `check_physics_material="0"` on `throw` suggests it might not depend on ground material.

### Other Animations

Includes animations for flying, knockback, and alerting.

```xml
  <!-- hovering -->
 <RectAnimation
  name="fly_idle"
  pos_x="0"
  pos_y="0"
  frame_count="6"
  frame_width="16"
  frame_height="24"
  frame_wait="0.2"
  frames_per_row="12"
  loop="1" >
 </RectAnimation>
 
 <!-- flying -->
 <RectAnimation
  name="fly_move"
  pos_x="0"
  pos_y="24"
  frame_count="6"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="1" >
 </RectAnimation>

 <!-- knockback -->
 <RectAnimation
  name="knockback"
  pos_x="0"
  pos_y="192"
  frame_count="1"
  frame_width="16"
  frame_height="24"
  frame_wait="0.082"
  frames_per_row="12"
  loop="0" >
 </RectAnimation>
 
 <!-- knockback -->
 <RectAnimation
  name="alert"
  pos_x="0"
  pos_y="216"
  frame_count="5"
  frame_width="16"
  frame_height="24"
  frame_wait="0.15"
  frames_per_row="12"
  loop="0" >
 </RectAnimation>
```

### Key Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **pos\_x, pos\_y**: The starting coordinates of the animation frames on the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width, frame\_height**: Dimensions of a single frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are in a single row of the sprite sheet.
*   **loop**: `1` for looping animations, `0` for one-time animations.
*   **Event**: Triggers specific game actions at certain frames.
    *   **frame**: The frame number (0-indexed) when the event occurs.
    *   **name**: The name of the event (e.g., "step", "jump\_start", "throw", "hit").
    *   **probability**: Likelihood of the event occurring (usually 1).
    *   **check\_physics\_material**: If `1`, the event might depend on the material the entity is standing on.