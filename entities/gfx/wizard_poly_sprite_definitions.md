---
title: Wizard Poly Sprite Definitions
category: entities/gfx
---

# Wizard Poly Sprite Definitions

This document details the sprite and animation definitions for the "Wizard Poly" enemy in Noita, as found in `wizard_poly.xml`. This file is crucial for understanding how the enemy visually appears and animates within the game.

## Sprite Definition

The main `<Sprite>` tag defines the base visual properties and the primary sprite sheet used for the wizard.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/wizard_poly.png`
    *   The path to the image file containing all the wizard's graphical assets.
*   **`hotspots_filename`**: `data/enemies_gfx/wizard_hotspots.png`
    *   The path to a separate image file that defines specific points (hotspots) on the sprite, used for collision, aiming, or other game logic.
*   **`default_animation`**: `"stand"`
    *   The animation that plays by default when the sprite is first loaded or when no other animation is specified.
*   **`offset_x`**: `"8"`
    *   Horizontal offset applied to the sprite's position.
*   **`offset_y`**: `"14"`
    *   Vertical offset applied to the sprite's position.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation for the wizard.

### Animation Table:

| Name           | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Pos X | Pos Y | Loop | Shrink By One Pixel | Notes                               |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :---- | :---- | :--- | :------------------ | :---------------------------------- |
| `stand`        | 6           | 16          | 19           | 0.1        | 6              | 0     | 1     | -    | -                   | Default idle animation.             |
| `walk`         | 6           | 16          | 19           | 0.085      | 6              | 0     | 21    | -    | -                   | Walking animation.                  |
| `run`          | 6           | 16          | 19           | 0.085      | 6              | 0     | 21    | -    | -                   | Running animation.                  |
| `burn`         | 6           | 16          | 19           | 0.085      | 6              | 0     | 21    | -    | -                   | Animation when burning.             |
| `attack_ranged`| 7           | 17          | 20           | 0.08       | 6              | 0     | 41    | 0    | 1                   | Ranged attack animation.            |
| `fly_idle`     | 4           | 18          | 21           | 0.12       | 15             | 0     | 81    | -    | 1                   | Idle animation while flying.        |
| `fly_move`     | 4           | 18          | 21           | 0.12       | 15             | 0     | 102   | -    | 1                   | Movement animation while flying.    |

### Key Animation Elements:

*   **`name`**: The identifier for the animation (e.g., `stand`, `walk`, `attack_ranged`). This name is used by the game's AI and scripting to trigger specific animations.
*   **`frame_count`**: The total number of frames in this animation sequence.
*   **`frame_width`**, **`frame_height`**: The dimensions of each individual frame in pixels.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet for this animation. This is crucial for calculating the position of each frame.
*   **`pos_x`**, **`pos_y`**: The starting coordinates (top-left corner) of the animation's frames within the main sprite sheet.
*   **`loop`**: If set to `0`, the animation will not loop. By default, animations loop.
*   **`shrink_by_one_pixel`**: If set to `1`, the sprite is shrunk by one pixel, often used for animations that might otherwise overlap or appear too large.

## Animation Events

Some animations can have `<Event>` tags, which trigger specific game actions at certain frames.

### Example: `walk` animation events

The `walk` animation has two `step` events:

*   **`frame="0"`**: Triggers a "step" event on the first frame of the walk animation.
*   **`frame="3"`**: Triggers another "step" event on the fourth frame of the walk animation.

These events are configured with:

*   **`name="step"`**: The type of event.
*   **`check_physics_material="1"`**: Indicates that the game should check the physics material of the ground the wizard is standing on when this event occurs.
*   **`probability="1"`**: The event will always trigger when the specified frame is reached.
*   **`on_finished="0"`**: The event does not automatically finish the animation.

### Example: `attack_ranged` animation events

The `attack_ranged` animation has a `shoot_magic` event:

*   **`frame="5"`**: Triggers a "shoot\_magic" event on the sixth frame of the attack animation.
*   **`name="shoot_magic"`**: The type of event, likely responsible for spawning projectiles or initiating the wizard's magical attack.

## Hotspots

The `<Hotspot>` tag defines specific points of interest on the sprite.

### Example: `cape` hotspot

*   **`name="cape"`**: Identifies this hotspot as the "cape".
*   **`color="ff"`**: This likely refers to a color value used in the `wizard_hotspots.png` image to define the area or point for this hotspot. The exact interpretation of color values for hotspots can vary.

This information is essential for modders looking to alter the wizard's appearance, animations, or integrate custom behaviors tied to its visual states.