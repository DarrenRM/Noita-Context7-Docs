---
title: Boss Victory Room Mechanism Sprite
category: entities
---

# Boss Victory Room Mechanism Sprite

This XML file defines the sprite and animations for the victory room mechanism associated with the boss centipede in Noita.

## Sprite Definition

The primary sprite for the mechanism is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/boss_victoryroom_mechanism.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `46` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `138` - Vertical offset for the sprite's origin.
*   **default\_animation**: `default` - Sets the initial animation to play.

## Animations

The mechanism has two defined animations: `default` and `active`.

### `default` Animation

This is the initial, non-active state of the mechanism.

*   **name**: `default`
*   **frame\_count**: `1` - Indicates a single frame for this animation.
*   **frame\_width**: `143` - Width of each animation frame.
*   **frame\_height**: `205` - Height of each animation frame.
*   **frame\_wait**: `0.06` - Delay between frames (in seconds).
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - This animation does not loop.

### `active` Animation

This animation likely plays when the mechanism is activated or performing its function.

*   **name**: `active`
*   **frame\_count**: `8` - Total number of frames in this animation.
*   **frame\_width**: `143` - Width of each animation frame.
*   **frame\_height**: `205` - Height of each animation frame.
*   **frame\_wait**: `0.06` - Delay between frames (in seconds).
*   **frames\_per\_row**: `8` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - This animation will loop continuously.