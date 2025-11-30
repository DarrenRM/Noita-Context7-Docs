---
title: Player Hat 2 Sprite Animations
category: entities/gfx
---

# Player Hat 2 Sprite Animations

This document details the sprite animations for `player_hat2.xml`, which defines the visual frames for various player actions.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/player_hat2.png` - The path to the sprite sheet image.
*   **`default_animation`**: `stand` - The animation to play by default.
*   **`offset_x`**: `6` - Horizontal offset for the sprite.
*   **`offset_y`**: `14` - Vertical offset for the sprite.

## RectAnimation Elements

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "jump\_up").
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame in pixels.
*   **`frame_height`**: The height of each individual frame in pixels.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation's frame area on the sprite sheet.
*   **`loop`**: (Optional) If set to "0", the animation will not loop. Defaults to looping.
*   **`next_animation`**: (Optional) Specifies the animation to transition to after this one finishes (if not looping).
*   **`has_offset`**: (Optional) If set to "1", indicates that the `offset_x` and `offset_y` attributes within this animation should be used.
*   **`shrink_by_one_pixel`**: (Optional) If set to "1", the sprite will be shrunk by one pixel in each direction.

### Notable Animations:

| Animation Name             | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Loop | Notes                               |
| :------------------------- | :---------- | :---------- | :----------- | :------------- | :--- | :---------------------------------- |
| `stand`                    | 6           | 12          | 19           | 0.2            | Yes  | Default standing animation.         |
| `walk`                     | 6           | 12          | 19           | 0.105          | Yes  | Standard walking animation.         |
| `run`                      | 6           | 12          | 19           | 0.105          | Yes  | Faster movement animation.          |
| `jump_up`                  | 3           | 12          | 19           | 0.082          | No   | Animation for jumping upwards.      |
| `jump_fall`                | 3           | 12          | 19           | 0.082          | No   | Animation for falling after jump.   |
| `land`                     | 3           | 12          | 19           | 0.075          | No   | Animation for landing.              |
| `fly_idle`                 | 4           | 12          | 19           | 0.09           | Yes  | Idle animation while flying.        |
| `fly_move`                 | 4           | 13          | 20           | 0.12           | Yes  | Movement animation while flying.    |
| `knockback`                | 4           | 13          | 20           | 0.06           | Yes  | Animation when being knocked back.  |
| `swim_idle`                | 4           | 13          | 20           | 0.08           | Yes  | Idle animation while swimming.      |
| `swim_move`                | 5           | 13          | 20           | 0.11           | Yes  | Movement animation while swimming.  |
| `attack`                   | 6           | 13          | 20           | 0.11           | No   | General attack animation.           |
| `kick`                     | 6           | 13          | 20           | 0.11           | No   | Kick attack animation.              |
| `telekinesis_throw`        | 4           | 13          | 20           | 0.06           | No   | Animation for throwing with TK.     |
| `lower_head`               | 3           | 12          | 19           | 0.05           | No   | Animation for lowering the head.    |
| `raise_head`               | 3           | 12          | 19           | 0.05           | No   | Animation for raising the head.     |
| `eat`                      | 11          | 12          | 19           | 0.07           | No   | Eating animation.                   |
| `crouch`                   | 1           | 12          | 19           | 0.14           | Yes  | Crouching animation.                |
| `walk_backwards`           | 6           | 12          | 19           | 0.105          | Yes  | Walking backwards animation.        |
| `move_item_stash`          | 5           | 12          | 19           | 0.07           | No   | Moving item to stash animation.     |
| `move_item`                | 4           | 12          | 19           | 0.09           | No   | Moving item animation.              |
| `throw_old`                | 5           | 12          | 19           | 0.09           | No   | Older throwing animation.           |
| `stand_crouched`           | 6           | 12          | 19           | 0.2            | Yes  | Standing while crouched.            |
| `walk_crouched`            | 6           | 12          | 19           | 0.095          | Yes  | Walking while crouched.             |
| `run_crouched`             | 6           | 12          | 19           | 0.095          | Yes  | Running while crouched.             |
| `walk_backwards_crouched`  | 6           | 12          | 19           | 0.095          | Yes  | Walking backwards while crouched.   |
| `telekinesis_throw_crouched` | 4           | 13          | 20           | 0.06           | No   | TK throw while crouched.            |
| `kick_crouched`            | 6           | 13          | 20           | 0.11           | No   | Kick attack while crouched.         |
| `kick_alt_crouched`        | 6           | 13          | 20           | 0.11           | No   | Alternate kick while crouched.      |
| `throw_crouched`           | 5           | 12          | 19           | 0.09           | No   | Throwing animation while crouched.  |
| `rise`                     | 5           | 12          | 19           | 0.11           | No   | Rising animation.                   |
| `throw`                    | 5           | 12          | 19           | 0.07           | No   | General throwing animation.         |
| `slide`                    | 4           | 12          | 19           | 0.08           | Yes  | Sliding animation.                  |
| `slide_end`                | 3           | 12          | 19           | 0.06           | No   | End of slide animation.             |
| `slide_crouched`           | 4           | 12          | 19           | 0.08           | Yes  | Sliding while crouched.             |
| `slide_end_crouched`       | 3           | 12          | 19           | 0.06           | No   | End of crouched slide animation.    |
| `slide_start`              | 2           | 12          | 19           | 0.05           | No   | Start of slide animation.           |
| `slide_start_crouched`     | 2           | 12          | 19           | 0.05           | No   | Start of crouched slide animation.  |
| `hurt`                     | 3           | 12          | 19           | 0.08           | No   | Hurt animation.                     |
| `hurt_swim`                | 3           | 12          | 19           | 0.08           | No   | Hurt animation while swimming.      |
| `hurt_fly`                 | 3           | 12          | 19           | 0.08           | No   | Hurt animation while flying.        |
| `grab_item`                | 9           | 12          | 19           | 0.1            | No   | Grabbing an item animation.         |
| `idle_hold`                | 6           | 12          | 19           | 0.24           | Yes  | Idle animation while holding something. |
| `throw_item`               | 10          | 13          | 20           | 0.07           | No   | Throwing an item animation.         |
| `push_start`               | 4           | 12          | 19           | 0.09           | No   | Start of push animation.            |
| `push`                     | 6           | 12          | 19           | 0.12           | Yes  | Pushing animation.                  |
| `cough`                    | 6           | 12          | 19           | 0.09           | No   | Coughing animation.                 |
| `throw_small`              | 4           | 12          | 19           | 0.08           | No   | Throwing a small item animation.    |
| `intro_stand_up`           | 21          | 20          | 22           | 0.15           | No   | Animation for standing up from intro. |
| `intro_sleep`              | 6           | 21          | 23           | 0.15           | No   | Animation for sleeping intro.       |
| `telekinesis_grab_start`   | 6           | 15          | 19           | 0.06           | No   | Start of TK grab animation.         |
| `telekinesis_grab_start_crouched` | 6           | 15          | 19           | 0.06           | No   | Start of crouched TK grab.          |