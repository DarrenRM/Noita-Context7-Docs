---
title: Player Amulet Sprite Definitions
category: entities/gfx
---

# Player Amulet Sprite Definitions

This document details the sprite definitions for the player's amulet in Noita, as found in `player_amulet.xml`. It outlines the various animations and their properties, which are crucial for understanding and modifying character visuals.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

*   **`filename`**: `data/enemies_gfx/player_amulet.png` - The path to the sprite sheet.
*   **`offset_x`**: `6` - Horizontal offset for the sprite.
*   **`offset_y`**: `14` - Vertical offset for the sprite.
*   **`default_animation`**: `"stand"` - The animation to play by default.

## Key Animation Definitions

Each `<RectAnimation>` tag defines a specific animation. The following are key attributes and a selection of important animations:

### Core Attributes for Animations

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "jump_up").
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame in pixels.
*   **`frame_height`**: The height of each individual frame in pixels.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`pos_x`**: The X-coordinate (in pixels) of the top-left corner of the animation's frame grid on the sprite sheet.
*   **`pos_y`**: The Y-coordinate (in pixels) of the top-left corner of the animation's frame grid on the sprite sheet.
*   **`loop`**: `0` for non-looping animations (play once), `1` for looping animations.
*   **`shrink_by_one_pixel`**: If `1`, the sprite is shrunk by one pixel, often used for animations with slightly different dimensions.
*   **`has_offset`**: If `1`, applies `offset_x` and `offset_y` specific to this animation.
*   **`next_animation`**: Specifies the animation to transition to after this one finishes (if `loop="0"`).

### Notable Animations

| Animation Name              | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Loop | Notes                                     |
| :-------------------------- | :---------- | :---------- | :----------- | :------------- | :--- | :---------------------------------------- |
| `stand`                     | 6           | 12          | 19           | 0.2            | 1    | Default idle animation.                   |
| `walk`                      | 6           | 12          | 19           | 0.105          | 1    | Standard walking animation.               |
| `run`                       | 6           | 12          | 19           | 0.105          | 1    | Faster movement animation.                |
| `burn`                      | 6           | 12          | 19           | 0.095          | 1    | Animation for being on fire.              |
| `jump_up`                   | 3           | 12          | 19           | 0.082          | 0    | Ascending jump animation.                 |
| `jump_fall`                 | 3           | 12          | 19           | 0.082          | 0    | Falling after a jump.                     |
| `land`                      | 3           | 12          | 19           | 0.075          | 0    | Landing animation.                        |
| `fly_idle`                  | 4           | 12          | 19           | 0.09           | 1    | Idle animation while flying.              |
| `fly_move`                  | 4           | 13          | 20           | 0.12           | 1    | Movement animation while flying.          |
| `knockback`                 | 4           | 13          | 20           | 0.06           | 1    | Animation when being hit and pushed back. |
| `swim_idle`                 | 4           | 13          | 20           | 0.08           | 1    | Idle animation while swimming.            |
| `swim_move`                 | 5           | 13          | 20           | 0.11           | 1    | Movement animation while swimming.        |
| `attack`                    | 6           | 13          | 20           | 0.11           | 0    | General attack animation.                 |
| `kick`                      | 6           | 13          | 20           | 0.11           | 0    | Kick attack animation.                    |
| `kick_alt`                  | 6           | 13          | 20           | 0.11           | 0    | Alternative kick animation.               |
| `lower_head`                | 3           | 12          | 19           | 0.05           | 0    | Animation for lowering the head.          |
| `raise_head`                | 3           | 12          | 19           | 0.05           | 0    | Animation for raising the head.           |
| `eat`                       | 11          | 12          | 19           | 0.07           | 0    | Eating animation.                         |
| `crouch`                    | 1           | 12          | 19           | 0.14           | 1    | Crouching animation.                      |
| `walk_backwards`            | 6           | 12          | 19           | 0.105          | 1    | Walking backward animation.               |
| `move_item_stash`           | 5           | 12          | 19           | 0.07           | 0    | Animation for stashing an item.           |
| `move_item`                 | 4           | 12          | 19           | 0.09           | 0    | Animation for moving an item.             |
| `throw_old`                 | 5           | 12          | 19           | 0.09           | 0    | Older throw animation.                    |
| `stand_crouched`            | 6           | 12          | 19           | 0.2            | 1    | Standing while crouched.                  |
| `walk_crouched`             | 6           | 12          | 19           | 0.095          | 1    | Walking while crouched.                   |
| `run_crouched`              | 6           | 12          | 19           | 0.095          | 1    | Running while crouched.                   |
| `walk_backwards_crouched`   | 6           | 12          | 19           | 0.095          | 1    | Walking backward while crouched.          |
| `kick_crouched`             | 6           | 13          | 20           | 0.11           | 0    | Kick attack while crouched.               |
| `kick_alt_crouched`         | 6           | 13          | 20           | 0.11           | 0    | Alternative kick attack while crouched.   |
| `throw_crouched`            | 5           | 12          | 19           | 0.09           | 0    | Throwing while crouched.                  |
| `rise`                      | 5           | 12          | 19           | 0.11           | 0    | Animation for rising up.                  |
| `throw`                     | 5           | 12          | 19           | 0.07           | 0    | Standard throw animation.                 |
| `slide`                     | 4           | 12          | 19           | 0.08           | 1    | Sliding animation.                        |
| `slide_end`                 | 3           | 12          | 19           | 0.06           | 0    | End of slide animation.                   |
| `slide_crouched`            | 4           | 12          | 19           | 0.08           | 1    | Sliding while crouched.                   |
| `slide_end_crouched`        | 3           | 12          | 19           | 0.06           | 0    | End of crouched slide animation.          |
| `slide_start`               | 2           | 12          | 19           | 0.05           | 0    | Start of slide animation.                 |
| `slide_start_crouched`      | 2           | 12          | 19           | 0.05           | 0    | Start of crouched slide animation.        |
| `hurt`                      | 3           | 12          | 19           | 0.08           | 0    | Hurt animation.                           |
| `hurt_swim`                 | 3           | 12          | 19           | 0.08           | 0    | Hurt animation while swimming.            |
| `hurt_fly`                  | 3           | 12          | 19           | 0.08           | 0    | Hurt animation while flying.              |
| `grab_item`                 | 9           | 12          | 19           | 0.1            | 0    | Animation for grabbing an item.           |
| `idle_hold`                 | 6           | 12          | 19           | 0.24           | 1    | Idle animation while holding something.   |
| `throw_item`                | 10          | 13          | 20           | 0.07           | 0    | Animation for throwing an item.           |
| `push_start`                | 4           | 12          | 19           | 0.09           | 0    | Start of push animation.                  |
| `push`                      | 6           | 12          | 19           | 0.12           | 1    | Pushing animation.                        |
| `cough`                     | 6           | 12          | 19           | 0.09           | 0    | Coughing animation.                       |
| `intro_stand_up`            | 21          | 20          | 22           | 0.15           | 0    | Animation for standing up at intro.       |
| `intro_sleep`               | 6           | 20          | 22           | 0.15           | 1    | Sleeping animation at intro.              |
| `throw_small`               | 4           | 12          | 19           | 0.08           | 0    | Animation for throwing small objects.     |
| `telekinesis_grab_start`    | 6           | 15          | 19           | 0.06           | 0    | Start of telekinesis grab.                |
| `telekinesis_grab_start_crouched` | 6 | 15          | 19           | 0.06           | 0    | Start of crouched telekinesis grab.       |
| `telekinesis_throw`         | 4           | 13          | 20           | 0.06           | 0    | Telekinesis throw animation.              |
| `telekinesis_throw_crouched`| 4           | 13          | 20           | 0.06           | 0    | Crouched telekinesis throw animation.     |

This XML file defines the visual representation of the player's amulet across various actions and states, providing a foundation for animation-related modding.