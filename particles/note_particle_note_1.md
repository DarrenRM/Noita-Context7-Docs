---
title: Note Particle (note_1)
category: guides
---

<Sprite
filename="data/particles/note_1.png"
offset_x="4"
offset_y="4"
default_animation="explosion"
>

<!-- explosion -->
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="1"
frame_width="8"
frame_height="8"
frame_wait="0.02"
frames_per_row="1"
loop="1"
>
</RectAnimation>
</Sprite>
```

---
title: Note Particle (note_1)
category: particles
---

# Note Particle (note_1)

This documentation describes the `note_1.xml` file, which defines a simple particle effect in Noita.

## Sprite Definition

The primary element is `<Sprite>`, which defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: Specifies the texture file for the particle.
    *   `data/particles/note_1.png`
*   **`offset_x`**, **`offset_y`**: Adjust the sprite's position relative to its origin.
    *   `offset_x="4"`
    *   `offset_y="4"`
*   **`default_animation`**: The name of the animation to play by default.
    *   `default_animation="explosion"`

## Animation Definition

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by `default_animation`.
    *   `name="explosion"`
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the sprite sheet.
    *   `pos_x="0"`
    *   `pos_y="0"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `frame_count="1"`
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame.
    *   `frame_width="8"`
    *   `frame_height="8"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `frame_wait="0.02"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `frames_per_row="1"`
*   **`loop`**: Determines if the animation should repeat.
    *   `loop="1"` (1 indicates true, meaning it loops)