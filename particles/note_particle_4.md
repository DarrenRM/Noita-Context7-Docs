---
title: Note Particle (4)
category: guides
---

<Sprite
filename="data/particles/note_4.png"
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
title: Note Particle (4)
category: particles
---

# Note Particle (4)

This document describes the configuration for a specific particle effect in Noita, identified as "note_4". This particle is likely used to represent a musical note or a similar auditory cue within the game.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`filename`**: `data/particles/note_4.png` - Specifies the image file used for the particle's sprite.
*   **`offset_x`**: `4` - The horizontal offset of the sprite.
*   **`offset_y`**: `4` - The vertical offset of the sprite.
*   **`default_animation`**: `explosion` - The name of the animation that plays by default when this particle is spawned.

## Animation Details

The particle utilizes a single animation named "explosion".

### Animation: `explosion`

This `<RectAnimation>` element defines the visual sequence for the particle.

#### Key Attributes:

*   **`name`**: `explosion` - The identifier for this animation.
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `0` - The starting Y position of the animation frames within the sprite sheet.
*   **`frame_count`**: `1` - The total number of frames in this animation.
*   **`frame_width`**: `8` - The width of each individual animation frame.
*   **`frame_height`**: `8` - The height of each individual animation frame.
*   **`frame_wait`**: `0.02` - The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that the animation should loop (play repeatedly).