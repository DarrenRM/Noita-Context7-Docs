---
title: Spitmonster Sprite Animations
category: data/enemies_gfx
---

# Spitmonster Sprite Animations

This document details the sprite animations for the Spitmonster enemy in Noita, as defined in its `spitmonster.xml` file. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/spitmonster.png` - The path to the sprite sheet.
*   **offset\_x**: `12` - Horizontal offset for the sprite.
*   **offset\_y**: `20` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation: `stand`

*   **frame\_count**: `6`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.2` (seconds per frame)
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `1`
*   **shrink\_by\_one\_pixel**: `1`

### Animation: `walk`

*   **frame\_count**: `6`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.12`
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events within `walk`:

*   **frame `0`**: Triggers `"step"` event.
*   **frame `3`**: Triggers `"step"` event.

### Animation: `run`

*   **frame\_count**: `6`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.12`
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events within `run`:

*   **frame `0`**: Triggers `"step"` event.
*   **frame `3`**: Triggers `"step"` event.

### Animation: `burn`

*   **frame\_count**: `6`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.12`
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **pos\_x**: `0`
*   **pos\_y**: `26`
*   **shrink\_by\_one\_pixel**: `1`

#### Events within `burn`:

*   **frame `0`**: Triggers `"step"` event.
*   **frame `3`**: Triggers `"step"` event.

### Animation: `jump_up`

*   **frame\_count**: `1`
*   **frame\_height**: `24`
*   **frame\_wait**: `0.082`
*   **frame\_width**: `24`
*   **frames\_per\_row**: `8`
*   **loop**: `0` (Does not loop)
*   **pos\_x**: `0`
*   **pos\_y**: `51`

#### Events within `jump_up`:

*   **frame `0`**: Triggers `"jump"` event.

### Animation: `jump_fall`

*   **frame\_count**: `1`
*   **frame\_height**: `24`
*   **frame\_wait**: `0.082`
*   **frame\_width**: `24`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **pos\_x**: `0`
*   **pos\_y**: `76`

### Animation: `attack`

*   **frame\_count**: `7`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.075`
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **pos\_x**: `0`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

#### Events within `attack`:

*   **frame `3`**: Triggers `"shoot_magic"`, `"attack_shoot"`, and `"voc_attack"` events.

### Animation: `attack_ranged`

*   **frame\_count**: `7`
*   **frame\_height**: `25`
*   **frame\_wait**: `0.075`
*   **frame\_width**: `25`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **pos\_x**: `0`
*   **pos\_y**: `101`
*   **shrink\_by\_one\_pixel**: `1`

#### Events within `attack_ranged`:

*   **frame `3`**: Triggers `"shoot_magic"` and `"attack_shoot"` events.

## Event Definitions

Events within animations can trigger specific game actions.

### Key Event Attributes:

*   **name**: The name of the event (e.g., `step`, `jump`, `shoot_magic`).
*   **frame**: The frame number within the animation when the event occurs.
*   **probability**: The chance of the event occurring (usually `1` for guaranteed events).
*   **on\_finished**: `0` indicates the event does not stop the animation.
*   **check\_physics\_material**: `1` means the event's behavior might depend on the physics material of the ground.

---