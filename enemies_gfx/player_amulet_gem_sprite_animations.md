---
title: Player Amulet Gem Sprite Animations
category: entities_gfx
---

# Player Amulet Gem Sprite Animations

This document details the sprite animations for the player's amulet gem, as defined in the `player_amulet_gem.xml` file. This file specifies the visual frames and timing for various player actions.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and default animation.

### Key Attributes

*   **filename**: `data/enemies_gfx/player_amulet_gem.png` - The path to the sprite sheet.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `<RectAnimation>`

*   **name**: The identifier for the animation (e.g., "stand", "walk", "jump\_up").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet (in pixels).
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet (in pixels).
*   **loop**: `0` indicates the animation plays once, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel, often used for animations with slightly different dimensions.
*   **next\_animation**: Specifies the animation to transition to after this one completes (e.g., for sequential animations like `intro_stand_up` transitioning to `stand`).
*   **has\_offset**: `1` indicates that `offset_x` and `offset_y` defined within this animation should be used, overriding the main sprite's offsets.

### Notable Animations

| Animation Name                 | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Loop | Notes                                     |
| :----------------------------- | :---------- | :---------- | :----------- | :------------- | :--- | :---------------------------------------- |
| `stand`                        | 6           | 12          | 19           | 0.2            | 1    | Default idle animation.                   |
| `walk`                         | 6           | 12          | 19           | 0.105          | 1    | Standard walking animation.               |
| `run`                          | 6           | 12          | 19           | 0.105          | 1    | Running animation.                        |
| `jump_up`                      | 3           | 12          | 19           | 0.082          | 0    | Jumping upwards.                          |
| `jump_fall`                    | 3           | 12          | 19           | 0.082          | 0    | Falling after jump.                       |
| `land`                         | 3           | 12          | 19           | 0.075          | 0    | Landing animation.                        |
| `fly_idle`                     | 4           | 12          | 19           | 0.09           | 1    | Idle animation while flying.              |
| `fly_move`                     | 4           | 13          | 20           | 0.12           | 1    | Movement animation while flying.          |
| `knockback`                    | 4           | 13          | 20           | 0.06           | 1    | Animation when hit and pushed back.       |
| `swim_idle`                    | 4           | 13          | 20           | 0.08           | 1    | Idle animation while swimming.            |
| `swim_move`                    | 5           | 13          | 20           | 0.11           | 1    | Movement animation while swimming.        |
| `attack`                       | 6           | 13          | 20           | 0.11           | 0    | General attack animation.                 |
| `kick`                         | 6           | 13          | 20           | 0.11           | 0    | Kick attack animation.                    |
| `hurt`                         | 3           | 12          | 19           | 0.08           | 0    | Taking damage animation.                  |
| `intro_stand_up`               | 21          | 20          | 22           | 0.15           | 0    | Initial animation when standing up.       |
| `telekinesis_grab_start`       | 6           | 15          | 19           | 0.06           | 0    | Start of telekinesis grab.                |
| `telekinesis_throw`            | 4           | 13          | 20           | 0.06           | 0    | Telekinesis throwing animation.           |

**Note:** Many animations share similar frame dimensions and `frames_per_row` values, indicating they are likely sourced from contiguous blocks on the sprite sheet. Animations with `shrink_by_one_pixel="1"` and different frame dimensions (e.g., 13x20) are typically for actions like flying, swimming, or attacking. The `pos_x` and `pos_y` attributes are crucial for correctly slicing these animations from the sprite sheet.