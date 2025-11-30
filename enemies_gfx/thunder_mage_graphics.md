---
title: Thunder Mage Graphics
category: data/enemies_gfx
---

# Thunder Mage Graphics

This document details the graphical assets and animations for the Thunder Mage enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The main sprite definition for the Thunder Mage.

```xml
<Sprite 
  filename="data/enemies_gfx/thundermage.png" 
  offset_x="9" 
  offset_y="19"
  default_animation="stand" >
  <!-- ... animations ... -->
</Sprite>
```

*   **filename**: Path to the sprite sheet image.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's pivot point.
*   **default\_animation**: The animation to play when the entity is idle.

## Animations

The Thunder Mage has several distinct animations, each defined by a `RectAnimation` tag.

### Stand Animation

The default idle animation.

```xml
<RectAnimation 
  frame_count="8" 
  frame_height="24" 
  frame_wait="0.09" 
  frame_width="18" 
  frames_per_row="8" 
  name="stand" 
  pos_x="0" 
  pos_y="1" >
</RectAnimation>
```

*   **frame\_count**: Total number of frames in this animation.
*   **frame\_height**, **frame\_width**: Dimensions of each individual frame.
*   **frame\_wait**: Delay between frames in seconds.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The top-left corner of the animation's frame area within the sprite sheet.

### Walk Animation

Used when the Thunder Mage is moving.

```xml
<RectAnimation 
  frame_count="8" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="19" 
  frames_per_row="8" 
  name="walk" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <!-- ... events ... -->
</RectAnimation>
```

*   **shrink\_by\_one\_pixel**: A visual effect that slightly shrinks the sprite.
*   **Events**: Triggers specific actions at certain frames.

#### Walk Animation Events

*   **step**: Triggered at frames 2 and 6. This event likely plays footstep sounds or particles.
    *   `check_physics_material="1"`: The event's behavior might depend on the material it's interacting with.
    *   `max_distance="500"`: A parameter for the event's logic.

### Run Animation

Similar to walk, but potentially faster or more aggressive.

```xml
<RectAnimation 
  frame_count="8" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="19" 
  frames_per_row="8" 
  name="run" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <!-- ... events ... -->
</RectAnimation>
```

#### Run Animation Events

*   **step**: Triggered at frames 2 and 6, similar to the walk animation.

### Burn Animation

Visuals for when the Thunder Mage is on fire.

```xml
<RectAnimation 
  frame_count="8" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="19" 
  frames_per_row="8" 
  name="burn" 
  pos_x="0" 
  pos_y="26" 
  shrink_by_one_pixel="1" >
  <!-- ... events ... -->
</RectAnimation>
```

#### Burn Animation Events

*   **step**: Triggered at frames 2 and 6.

### Attack Animation

The primary melee or close-range attack animation.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="21" 
  frames_per_row="8" 
  has_offset="1" 
  loop="0" 
  name="attack" 
  offset_x="10" 
  offset_y="19" 
  pos_x="0" 
  pos_y="51" 
  shrink_by_one_pixel="1" >
  <!-- ... events ... -->
</RectAnimation>
```

*   **has\_offset**: Indicates that `offset_x` and `offset_y` are used for this animation.
*   **loop="0"**: This animation does not loop.
*   **offset\_x**, **offset\_y**: Specific offsets for this animation.

#### Attack Animation Events

*   **shoot\_thunder**: Triggered at frame 3. This event is responsible for the visual and functional aspect of the Thunder Mage's primary attack.
    *   `check_physics_material="0"`: This event's behavior is not dependent on the physics material.

### Fly Move Animation

Animation for when the Thunder Mage is flying.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="19" 
  frames_per_row="8" 
  name="fly_move" 
  pos_x="0" 
  pos_y="76" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Fly Idle Animation

Idle animation while flying.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="25" 
  frame_wait="0.09" 
  frame_width="19" 
  frames_per_row="8" 
  name="fly_idle" 
  pos_x="0" 
  pos_y="76" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Attack Ranged Animation

Animation for the Thunder Mage's ranged attack.

```xml
<RectAnimation 
  frame_count="10" 
  frame_height="25" 
  frame_wait="0.07" 
  frame_width="19" 
  frames_per_row="10" 
  loop="0" 
  name="attack_ranged" 
  pos_x="0" 
  pos_y="101" 
  shrink_by_one_pixel="1" >
  <!-- ... events ... -->
</RectAnimation>
```

*   **frame\_wait="0.07"**: This ranged attack animation plays slightly faster than other animations.

#### Attack Ranged Animation Events

*   **shoot\_thunder**: Triggered at frame 3. This event initiates the ranged thunder attack.
    *   `check_physics_material="0"`: Not dependent on physics material.