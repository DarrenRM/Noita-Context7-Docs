---
title: Boss Robot Body Sprite
category: entities
---

# Boss Robot Body Sprite

This documentation describes the sprite definition for the Boss Robot's body in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the entity.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_robot/body.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `22` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `22` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the entity is spawned.

## Animations

The `<Sprite>` tag can contain multiple animation definitions.

### `stand` Animation

This animation defines the "standing" pose for the Boss Robot's body.

#### Key Attributes:

*   **name**: `"stand"` - The identifier for this animation.
*   **pos\_x**: `"0"` - X-coordinate of the animation's starting frame within the sprite sheet.
*   **pos\_y**: `"0"` - Y-coordinate of the animation's starting frame within the sprite sheet.
*   **frame\_count**: `"6"` - The total number of frames in this animation.
*   **frame\_width**: `"44"` - The width of each individual frame.
*   **frame\_height**: `"44"` - The height of each individual frame.
*   **frame\_wait**: `"0.12"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `"6"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.