---
title: Player Hat 2 Shadow Sprite Animations
category: data/enemies_gfx
---

# Player Hat 2 Shadow Sprite Animations

This document details the sprite animations for `player_hat2_shadow.png`, used for the player's shadow appearance. It defines various animations for different player actions and states.

## Sprite Attributes

*   **filename**: `data/enemies_gfx/player_hat2_shadow.png` - The texture file for the sprite.
*   **offset\_x**: `6` - Horizontal offset for the sprite.
*   **offset\_y**: `14` - Vertical offset for the sprite.
*   **default\_animation**: `stand` - The animation to play by default.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation. Key attributes for each animation include:

*   **name**: The identifier for the animation (e.g., `stand`, `walk`, `jump_up`).
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **pos\_x**: The horizontal starting position of the animation frames within the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames within the sprite sheet.
*   **loop**: `0` indicates the animation plays once, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: If `1`, the sprite is shrunk by one pixel, often used for animations with slightly different dimensions.
*   **has\_offset**: If `1`, specific `offset_x` and `offset_y` values are used for this animation.
*   **offset\_x / offset\_y**: Specific offsets for animations that deviate from the default.
*   **next\_animation**: The animation to transition to after this one completes (if `loop="0"`).

### Key Animations

| Animation Name             | Frame Count | Frame Size (WxH) | Frame Wait (s) | Frames Per Row | Y Position | Notes                                     |
| :------------------------- | :---------- | :--------------- | :------------- | :------------- | :--------- | :---------------------------------------- |
| `stand`                    | 6           | 12x19            | 0.2            | 8              | 1          | Default idle animation.                   |
| `walk`                     | 6           | 12x19            | 0.105          | 8              | 21         | Standard walking animation.               |
| `run`                      | 6           | 12x19            | 0.105          | 8              | 21         | Faster movement animation.                |
| `jump_up`                  | 3           | 12x19            | 0.082          | 8              | 41         | Ascending jump animation.                 |
| `jump_fall`                | 3           | 12x19            | 0.082          | 8              | 61         | Descending jump animation.                |
| `land`                     | 3           | 12x19            | 0.075          | 8              | 81         | Landing animation.                        |
| `fly_idle`                 | 4           | 12x19            | 0.09           | 8              | 101        | Idle animation while flying.              |
| `fly_move`                 | 4           | 13x20            | 0.12           | 8              | 121        | Movement animation while flying.          |
| `knockback`                | 4           | 13x20            | 0.06           | 8              | 141        | Animation when taking damage/knockback.   |
| `attack`                   | 6           | 13x20            | 0.11           | 8              | 201        | Standard attack animation.                |
| `kick`                     | 6           | 13x20            | 0.11           | 8              | 201        | Kick attack animation.                    |
| `kick_alt`                 | 6           | 13x20            | 0.11           | 8              | 221        | Alternative kick attack animation.        |
| `hurt`                     | 3           | 12x19            | 0.08           | 8              | 661        | General hurt animation.                   |
| `intro_stand_up`           | 21          | 20x22            | 0.15           | 21             | 840        | Animation for standing up from a state.   |
| `telekinesis_grab_start`   | 6           | 15x19            | 0.06           | 12             | 884        | Start of telekinesis grab animation.      |
| `telekinesis_throw`        | 4           | 13x20            | 0.06           | 8              | 201        | Telekinesis throw animation (uses kick gfx). |

### Other Animations

The file also defines numerous other animations for various actions, including:

*   Crouching states (`crouch`, `stand_crouched`, `walk_crouched`, `run_crouched`, `kick_crouched`, `throw_crouched`, `slide_crouched`, `slide_end_crouched`, `slide_start_crouched`).
*   Swimming states (`swim_idle`, `swim_move`, `hurt_swim`).
*   Item interaction (`move_item_stash`, `move_item`, `throw_old`, `grab_item`, `idle_hold`, `throw_item`, `push_start`, `push`, `throw_small`).
*   Special actions (`burn`, `lower_head`, `raise_head`, `eat`, `rise`, `slide`, `slide_end`, `slide_start`, `hurt_fly`, `intro_sleep`, `telekinesis_grab_start_crouched`, `telekinesis_throw_crouched`).

These animations provide the visual feedback for a wide range of player activities and reactions.