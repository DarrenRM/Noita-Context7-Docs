---
title: Player Lukky Sprite Animations
category: entities/gfx
---

# Player Lukky Sprite Animations

This document details the sprite animations for the "Player Lukky" entity in Noita. It focuses on the key attributes of each animation, providing a concise overview for modding purposes.

## Sprite Sheet Information

The primary sprite sheet for Player Lukky is located at `data/enemies_gfx/player_lukky.png`.

### Key Sprite Attributes

*   **`default_animation`**: `stand` - The animation that plays by default.
*   **`filename`**: `data/enemies_gfx/player_lukky.png` - Path to the sprite sheet.
*   **`offset_x`**: `6` - Horizontal offset for the sprite.
*   **`offset_y`**: `14` - Vertical offset for the sprite.

## Animation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence. The following table summarizes the key attributes for each animation:

| Animation Name           | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Frames Per Row | Loop | Notes                               |
| :----------------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--- | :---------------------------------- |
| `stand`                  | 6           | 12          | 19           | 0.2            | 8              | Yes  | Default standing animation.         |
| `walk`                   | 6           | 12          | 19           | 0.105          | 8              | Yes  | Standard walking animation.         |
| `run`                    | 6           | 12          | 19           | 0.105          | 8              | Yes  | Running animation.                  |
| `burn`                   | 6           | 12          | 19           | 0.095          | 8              | Yes  | Animation when burning.             |
| `jump_up`                | 3           | 12          | 19           | 0.082          | 8              | No   | Jumping upwards.                    |
| `jump_fall`              | 3           | 12          | 19           | 0.082          | 8              | No   | Falling after jumping.              |
| `land`                   | 3           | 12          | 19           | 0.075          | 8              | No   | Landing animation.                  |
| `fly_idle`               | 4           | 12          | 19           | 0.09           | 8              | Yes  | Idle animation while flying.        |
| `fly_move`               | 4           | 13          | 20           | 0.12           | 8              | Yes  | Moving animation while flying.      |
| `knockback`              | 4           | 13          | 20           | 0.06           | 8              | Yes  | Animation when being knocked back.  |
| `swim_idle`              | 4           | 13          | 20           | 0.08           | 8              | Yes  | Idle animation while swimming.      |
| `swim_move`              | 5           | 13          | 20           | 0.11           | 8              | Yes  | Moving animation while swimming.    |
| `attack`                 | 6           | 13          | 20           | 0.11           | 8              | No   | General attack animation.           |
| `kick`                   | 6           | 13          | 20           | 0.11           | 8              | No   | Kick attack animation.              |
| `telekinesis_throw`      | 4           | 13          | 20           | 0.06           | 8              | No   | Telekinesis throwing animation.     |
| `kick_alt`               | 6           | 13          | 20           |0.11            | 8              | No   | Alternative kick animation.         |
| `lower_head`             | 3           | 12          | 19           | 0.05           | 8              | No   | Animation for lowering the head.    |
| `raise_head`             | 3           | 12          | 19           | 0.05           | 8              | No   | Animation for raising the head.     |
| `eat`                    | 11          | 12          | 19           | 0.07           | 11             | Yes  | Eating animation.                   |
| `crouch`                 | 1           | 12          | 19           | 0.14           | 8              | Yes  | Crouching animation.                |
| `walk_backwards`         | 6           | 12          | 19           | 0.105          | 8              | Yes  | Walking backwards animation.        |
| `move_item_stash`        | 5           | 12          | 19           | 0.07           | 8              | No   | Moving item into stash animation.   |
| `move_item`              | 4           | 12          | 19           | 0.09           | 8              | No   | Moving item animation.              |
| `throw_old`              | 5           | 13          | 20           | 0.09           | 8              | No   | Older throwing animation.           |
| `stand_crouched`         | 6           | 12          | 19           | 0.2            | 8              | Yes  | Standing while crouched.            |
| `walk_crouched`          | 6           | 12          | 19           | 0.095          | 8              | Yes  | Walking while crouched.             |
| `run_crouched`           | 6           | 12          | 19           | 0.095          | 8              | Yes  | Running while crouched.             |
| `walk_backwards_crouched`| 6           | 12          | 19           | 0.095          | 8              | Yes  | Walking backwards while crouched.   |
| `telekinesis_throw_crouched` | 4       | 13          | 20           | 0.06           | 8              | No   | Crouched telekinesis throw.         |
| `kick_crouched`          | 6           | 13          | 20           | 0.11           | 8              | No   | Crouched kick animation.            |
| `kick_alt_crouched`      | 6           | 13          | 20           | 0.11           | 8              | No   | Crouched alternative kick.          |
| `throw_crouched`         | 5           | 13          | 20           | 0.09           | 8              | No   | Crouched throwing animation.        |
| `rise`                   | 5           | 13          | 20           | 0.11           | 8              | No   | Rising animation.                   |
| `throw`                  | 5           | 13          | 20           | 0.07           | 8              | No   | General throwing animation.         |
| `slide`                  | 4           | 12          | 19           | 0.08           | 8              | Yes  | Sliding animation.                  |
| `slide_end`              | 3           | 12          | 19           | 0.06           | 8              | No   | End of slide animation.             |
| `slide_crouched`         | 4           | 12          | 19           | 0.08           | 8              | Yes  | Crouched sliding animation.         |
| `slide_end_crouched`     | 3           | 12          | 19           | 0.06           | 8              | No   | End of crouched slide.              |
| `slide_start`            | 2           | 12          | 19           | 0.05           | 8              | No   | Start of slide animation.           |
| `slide_start_crouched`   | 2           | 12          | 19           | 0.05           | 8              | No   | Start of crouched slide.            |
| `hurt`                   | 3           | 13          | 20           | 0.08           | 8              | No   | Hurt animation (general).           |
| `hurt_swim`              | 3           | 12          | 19           | 0.08           | 8              | No   | Hurt animation while swimming.      |
| `hurt_fly`               | 3           | 12          | 19           | 0.08           | 8              | No   | Hurt animation while flying.        |
| `grab_item`              | 9           | 12          | 19           | 0.1            | 9              | No   | Grabbing an item animation.         |
| `idle_hold`              | 6           | 12          | 19           | 0.24           | 8              | Yes  | Idle animation while holding something. |
| `throw_item`             | 10          | 13          | 20           | 0.07           | 10             | No   | Throwing an item animation.         |
| `push_start`             | 4           | 12          | 19           | 0.09           | 8              | No   | Starting to push animation.         |
| `push`                   | 6           | 12          | 19           | 0.12           | 8              | Yes  | Pushing animation.                  |
| `cough`                  | 6           | 12          | 19           | 0.09           | 8              | No   | Coughing animation.                 |
| `throw_small`            | 4           | 13          | 20           | 0.08           | 8              | No   | Throwing a small item.              |
| `intro_stand_up`         | 21          | 20          | 22           | 0.15           | 21             | No   | Animation for standing up from intro. |
| `intro_sleep`            | 6           | 20          | 22           | 0.15           | 8              | Yes  | Sleeping animation for intro.       |
| `telekinesis_grab_start` | 6           | 15          | 19           | 0.06           | 12             | No   | Starting telekinesis grab.          |
| `telekinesis_grab_start_crouched` | 6 | 15          | 19           | 0.06           | 12             | No   | Starting crouched telekinesis grab. |

### Key Animation Attributes Explained

*   **`name`**: The identifier for the animation, used by the game to trigger it.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width` / `frame_height`**: Dimensions of each individual frame in pixels.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
*   **`frames_per_row`**: How many frames are laid out horizontally on the sprite sheet.
*   **`loop`**: If set to `0`, the animation plays only once. If omitted or set to `1` (or not present), it loops.
*   **`pos_x` / `pos_y`**: The starting X and Y coordinates (in pixels) of the animation's first frame on the sprite sheet. These are relative to the top-left of the sprite sheet.
*   **`offset_x` / `offset_y`**: Applied to the `Sprite` tag, these define the sprite's pivot point relative to its bounding box.
*   **`shrink_by_one_pixel`**: A flag that slightly shrinks the sprite's bounding box, often used for animations with slightly different dimensions to maintain consistency.
*   **`has_offset`**: Indicates if the `offset_x` and `offset_y` attributes on the `<RectAnimation>` tag should be used.
*   **`next_animation`**: Specifies which animation should play after this one finishes (e.g., `intro_stand_up` transitions to `stand`).