---
title: Plague Rat Sprite Animations
category: entities/enemies_gfx
---

# Plague Rat Sprite Animations

This document details the sprite animations for the Plague Rat enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Plague Rat.

```xml
<Sprite 
  filename="data/enemies_gfx/plague_rat.png" 
  offset_x="20" 
  offset_y="12"
  default_animation="stand" >
  <!-- Animation definitions follow -->
</Sprite>
```

### Key Attributes:

*   **filename**: Path to the sprite image file.
*   **offset\_x, offset\_y**: Adjusts the sprite's position relative to its origin.
*   **default\_animation**: The animation to play by default.

## Animations

The Plague Rat has several distinct animations, each defined by a `RectAnimation` tag.

### `stand` Animation

The idle animation for the Plague Rat.

```xml
<RectAnimation 
  frame_count="5" 
  frame_height="20" 
  frame_wait="0.1" 
  frame_width="20" 
  frames_per_row="6" 
  name="stand" 
  pos_x="0" 
  pos_y="1" >
</RectAnimation>
```

*   **frame\_count**: Total number of frames in this animation.
*   **frame\_height, frame\_width**: Dimensions of each individual frame.
*   **frame\_wait**: Delay between frames in seconds.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **name**: The identifier for this animation.
*   **pos\_x, pos\_y**: The starting position of the animation frames within the sprite sheet.

### `walk` Animation

The animation for when the Plague Rat is walking.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="20" 
  frame_wait="0.06" 
  frame_width="20" 
  frames_per_row="8" 
  name="walk" 
  pos_x="0" 
  pos_y="22" >
  <!-- Events can be defined here -->
</RectAnimation>
```

*   **frame\_wait**: Faster frame rate for movement.
*   **pos\_y**: Starts on a different row of the sprite sheet compared to `stand`.
*   **Events**: This animation includes `step` events.

#### `step` Event (within `walk`)

Triggered during the walk animation.

```xml
<Event 
  check_physics_material="1" 
  frame="0" 
  max_distance="500" 
  name="step" 
  on_finished="0" 
  probability="1" >
</Event>
```

*   **frame**: The frame number at which this event occurs.
*   **name**: The name of the event (e.g., "step").
*   **check\_physics\_material**: If set to 1, checks the material under the entity.
*   **probability**: Likelihood of the event triggering.

### `run` Animation

Similar to `walk`, but likely intended for faster movement.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="20" 
  frame_wait="0.06" 
  frame_width="20" 
  frames_per_row="8" 
  name="run" 
  pos_x="0" 
  pos_y="22" >
  <!-- Events can be defined here -->
</RectAnimation>
```

*   Shares frame structure and `step` events with `walk`.

### `burn` Animation

Animation for when the Plague Rat is on fire.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="20" 
  frame_wait="0.06" 
  frame_width="20" 
  frames_per_row="8" 
  name="burn" 
  pos_x="0" 
  pos_y="22" >
  <!-- Events can be defined here -->
</RectAnimation>
```

*   Shares frame structure and `step` events with `walk` and `run`.

### `jump_up` Animation

Animation for the upward phase of a jump.

```xml
<RectAnimation 
  frame_count="3" 
  frame_height="20" 
  frame_wait="0.082" 
  frame_width="20" 
  frames_per_row="8" 
  loop="0" 
  name="jump_up" 
  pos_x="0" 
  pos_y="43" >
  <!-- Events can be defined here -->
</RectAnimation>
```

*   **loop="0"**: This animation does not loop.
*   **pos\_y**: Uses a different sprite sheet row.
*   **Events**: Includes a `jump` event on frame 0.

#### `jump` Event (within `jump_up`)

Triggered at the start of the jump.

```xml
<Event 
  check_physics_material="1" 
  frame="0" 
  max_distance="500" 
  name="jump" 
  on_finished="0" 
  probability="1" >
</Event>
```

### `jump_fall` Animation

Animation for the falling phase of a jump.

```xml
<RectAnimation 
  frame_count="2" 
  frame_height="20" 
  frame_wait="0.082" 
  frame_width="20" 
  frames_per_row="8" 
  loop="0" 
  name="jump_fall" 
  pos_x="0" 
  pos_y="64" >
</RectAnimation>
```

*   **loop="0"**: This animation does not loop.
*   **pos\_y**: Uses a different sprite sheet row.

### `attack` Animation

Animation for the Plague Rat's attack.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="21" 
  frame_wait="0.08" 
  frame_width="21" 
  frames_per_row="8" 
  loop="0" 
  name="attack" 
  pos_x="0" 
  pos_y="85" 
  shrink_by_one_pixel="1" >
  <!-- Events can be defined here -->
</RectAnimation>
```

*   **frame\_height, frame\_width**: Slightly different dimensions.
*   **loop="0"**: This animation does not loop.
*   **pos\_y**: Uses a different sprite sheet row.
*   **shrink\_by\_one\_pixel="1"**: Indicates a minor adjustment to the sprite's bounding box.
*   **Events**: Includes an `attack_bite` event.

#### `attack_bite` Event (within `attack`)

Triggered during the attack animation.

```xml
<Event 
  check_physics_material="0" 
  frame="2" 
  max_distance="500" 
  name="attack_bite" 
  on_finished="0" 
  probability="1" >
</Event>
```

*   **check\_physics\_material="0"**: This event does not check the physics material.
*   **frame="2"**: Occurs on the third frame of the attack animation.
*   **name="attack\_bite"**: Identifies the specific attack action.