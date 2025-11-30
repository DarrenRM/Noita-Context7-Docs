---
title: Spell Levitate Sprite
category: data/temp/spells
---

---

# Spell Levitate Sprite

This documentation describes the sprite data for the "Levitate" spell in Noita, focusing on its visual representation and animation.

## Sprite Definition

The core sprite definition for the Levitate spell is as follows:

```xml
<Sprite
 filename="data/temp/spells/spell_levitate.png"
 offset_x="12"
 offset_y="12" >
  <!-- ... animations ... -->
</Sprite>
```

*   **`filename`**: Specifies the path to the sprite image file.
*   **`offset_x`**, **`offset_y`**: Define the pixel offset for the sprite's origin.

## Animations

The spell sprite includes two distinct animations: `mouse_over` and `mouse_out`, likely for interactive states.

### `mouse_over` Animation

This animation is triggered when the mouse hovers over the spell icon.

```xml
<RectAnimation
 name="mouse_over"
 pos_x="0"
 pos_y="0"
 frame_count="6"
 frame_width="24"
 frame_height="24"
 frame_wait="0.16"
 frames_per_row="6"
 loop="1" >
</RectAnimation>
```

*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Set to `1`, indicating this animation will loop continuously.

### `mouse_out` Animation

This animation is likely displayed when the mouse is not hovering over the spell icon.

```xml
<RectAnimation
 name="mouse_out"
 pos_x="0"
 pos_y="0"
 frame_count="1"
 frame_width="24"
 frame_height="24"
 frame_wait="3.0"
 frames_per_row="6"
 loop="0" >
</RectAnimation>
```

*   **`frame_count`**: Set to `1`, indicating a static frame.
*   **`frame_wait`**: A longer wait time, suggesting it's a default or idle state.
*   **`loop`**: Set to `0`, meaning this animation plays only once.