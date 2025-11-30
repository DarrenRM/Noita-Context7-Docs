---
title: Player Hat Sprite Animations
category: entities/enemies_gfx
---

# Player Hat Sprite Animations

This document details the sprite animations for the player's hat, as defined in `player_hat.xml`. It outlines the key attributes of the sprite and provides a summary of the various animations available.

## Sprite Attributes

The main `<Sprite>` element defines the base properties for all animations.

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`    | `data/enemies_gfx/player_hat.png`   | The path to the sprite sheet containing all animation frames.               |
| `default_animation` | `stand`                             | The animation to play by default when the sprite is first loaded.           |
| `offset_x`    | `6`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `14`                                | Vertical offset for the sprite's origin.                                    |

## Animation Definitions

Each `<RectAnimation>` element defines a specific animation sequence. The following table summarizes the key animations and their properties.

| Animation Name             | Frame Count | Frame Size (WidthxHeight) | Frame Wait (s) | Frames Per Row | Loop | Notes                               |
| :------------------------- | :---------- | :------------------------ | :------------- | :------------- | :--- | :---------------------------------- |
| `stand`                    | 6           | 12x19                     | 0.2            | 8              | Yes  | Default standing animation.         |
| `walk`                     | 6           | 12x19                     | 0.105          | 8              | Yes  | Walking animation.                  |
| `run`                      | 6           | 12x19                     | 0.105          | 8              | Yes  | Running animation.                  |
| `burn`                     | 6           | 12x19                     | 0.105          | 8              | Yes  | Animation for being on fire.        |
| `jump_up`                  | 3           | 12x19                     | 0.082          | 8              | No   | Jumping upwards.                    |
| `jump_fall`                | 3           | 12x19                     | 0.082          | 8              | No   | Falling after jumping.              |
| `land`                     | 3           | 13x19                     | 0.075          | 8              | No   | Landing animation. `shrink_by_one_pixel="1"` |
| `fly_idle`                 | 4           | 12x19                     | 0.09           | 8              | Yes  | Idle animation while flying.        |
| `fly_move`                 | 4           | 13x20                     | 0.12           | 8              | Yes  | Moving animation while flying. `shrink_by_one_pixel="1"` |
| `knockback`                | 4           | 13x20                     | 0.06           | 8              | Yes  | Animation when being knocked back. `shrink_by_one_pixel="1"` |
| `swim_idle`                | 4           | 13x20                     | 0.08           | 8              | Yes  | Idle animation while swimming. `shrink_by_one_pixel="1"` |
| `swim_move`                | 5           | 13x20                     | 0.11           | 8              | Yes  | Moving animation while swimming. `shrink_by_one_pixel="1"` |
| `attack`                   | 6           | 14x21                     | 0.11           | 8              | No   | General attack animation. `shrink_by_one_pixel="1"` |
| `kick`                     | 6           | 14x21                     | 0.11           | 8              | No   | Kick attack animation. `shrink_by_one_pixel="1"` |
| `telekinesis_throw`        | 4           | 14x21                     | 0.06           | 8              | No   | Telekinesis throw animation. `shrink_by_one_pixel="1"` |
| `kick_alt`                 | 6           | 14x21                     | 0.11           | 8              | No   | Alternative kick animation. `shrink_by_one_pixel="1"` |
| `lower_head`               | 3           | 13x20                     | 0.05           | 8              | No   | Animation for lowering the head. `shrink_by_one_pixel="1"` |
| `raise_head`               | 3           | 13x20                     | 0.05           | 8              | No   | Animation for raising the head. `shrink_by_one_pixel="1"` |
| `eat`                      | 11          | 13x20                     | 0.07           | 11             | Yes  | Eating animation. `shrink_by_one_pixel="1"` |
| `crouch`                   | 1           | 13x20                     | 0.14           | 8              | Yes  | Crouching animation. `shrink_by_one_pixel="1"` |
| `walk_backwards`           | 6           | 12x19                     | 0.105          | 8              | Yes  | Walking backwards animation.        |
| `move_item_stash`          | 5           | 12x19                     | 0.07           | 8              | No   | Moving item to stash animation.     |
| `move_item`                | 4           | 12x19                     | 0.09           | 8              | No   | Moving an item animation.           |
| `throw_old`                | 5           | 13x20                     | 0.09           | 8              | No   | Older throw animation. `shrink_by_one_pixel="1"` |
| `stand_crouched`           | 6           | 13x20                     | 0.2            | 8              | Yes  | Standing while crouched animation. `shrink_by_one_pixel="1"` |
| `walk_crouched`            | 6           | 13x20                     | 0.095          | 8              | Yes  | Walking while crouched animation. `shrink_by_one_pixel="1"` |
| `run_crouched`             | 6           | 13x20                     | 0.095          | 8              | Yes  | Running while crouched animation. `shrink_by_one_pixel="1"` |
| `walk_backwards_crouched`  | 6           | 13x20                     | 0.095          | 8              | Yes  | Walking backwards while crouched. `shrink_by_one_pixel="1"` |
| `telekinesis_throw_crouched` | 4           | 13x20                     | 0.06           | 8              | No   | Telekinesis throw while crouched. `shrink_by_one_pixel="1"` |
| `kick_crouched`            | 6           | 13x20                     | 0.11           | 8              | No   | Kick attack while crouched. `shrink_by_one_pixel="1"` |
| `kick_alt_crouched`        | 6           | 13x20                     | 0.11           | 8              | No   | Alternative kick while crouched. `shrink_by_one_pixel="1"` |
| `throw_crouched`           | 5           | 13x20                     | 0.09           | 8              | No   | Throw animation while crouched. `shrink_by_one_pixel="1"` |
| `rise`                     | 5           | 13x20                     | 0.11           | 8              | No   | Rising animation. `shrink_by_one_pixel="1"` |
| `throw`                    | 5           | 13x20                     | 0.07           | 8              | No   | General throw animation. `shrink_by_one_pixel="1"` |
| `slide`                    | 4           | 12x19                     | 0.08           | 8              | Yes  | Sliding animation.                  |
| `slide_end`                | 3           | 12x19                     | 0.06           | 8              | No   | End of slide animation.             |
| `slide_crouched`           | 4           | 13x20                     | 0.08           | 8              | Yes  | Sliding while crouched. `shrink_by_one_pixel="1"` |
| `slide_end_crouched`       | 3           | 13x20                     | 0.06           | 8              | No   | End of crouched slide. `shrink_by_one_pixel="1"` |
| `slide_start`              | 2           | 12x19                     | 0.05           | 8              | No   | Start of slide animation.           |
| `slide_start_crouched`     | 2           | 13x20                     | 0.05           | 8              | No   | Start of crouched slide. `shrink_by_one_pixel="1"` |
| `hurt`                     | 3           | 13x20                     | 0.08           | 8              | No   | Hurt animation. `shrink_by_one_pixel="1"` |
| `hurt_swim`                | 3           | 13x20                     | 0.08           | 8              | No   | Hurt animation while swimming. `shrink_by_one_pixel="1"` |
| `hurt_fly`                 | 3           | 13x20                     | 0.08           | 8              | No   | Hurt animation while flying. `shrink_by_one_pixel="1"` |
| `grab_item`                | 9           | 13x20                     | 0.1            | 9              | No   | Grabbing an item animation. `shrink_by_one_pixel="1"` |
| `idle_hold`                | 6           | 12x19                     | 0.24           | 8              | Yes  | Idle animation while holding something. |
| `throw_item`               | 10          | 13x20                     | 0.07           | 10             | No   | Throwing an item animation. `shrink_by_one_pixel="1"` |
| `push_start`               | 4           | 12x19                     | 0.09           | 8              | No   | Start of push animation.            |
| `push`                     | 6           | 13x20                     | 0.12           | 8              | Yes  | Pushing animation. `shrink_by_one_pixel="1"` |
| `cough`                    | 6           | 13x20                     | 0.09           | 8              | No   | Coughing animation. `shrink_by_one_pixel="1"` |
| `throw_small`              | 4           | 13x20                     | 0.08           | 8              | No   | Throwing a small item animation. `shrink_by_one_pixel="1"` |
| `intro_stand_up`           | 21          | 20x22                     | 0.15           | 21             | No   | Animation for standing up from intro. `has_offset="1"`, `offset_x="10"`, `offset_y="14"`, `next_animation="stand"` |
| `intro_sleep`              | 6           | 21x23                     | 0.15           | 8              | Yes  | Sleeping animation for intro. `has_offset="1"`, `offset_x="10"`, `offset_y="14"`, `shrink_by_one_pixel="1"` |
| `telekinesis_grab_start`  | 6           | 15x19                     | 0.06           | 12             | No   | Start of telekinesis grab.          |
| `telekinesis_grab_start_crouched` | 6           | 15x20                     | 0.06           | 12             | No   | Start of telekinesis grab while crouched. `shrink_by_one_pixel="1"` |

### Key Animation Attributes:

*   **`name`**: The identifier for the animation, used to trigger it in-game.
*   **`frame_count`**: The total number of frames in the animation sequence.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame in pixels.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: If set to `0` (or absent), the animation plays once. If absent or not `0`, it loops.
*   **`pos_x`**, **`pos_y`**: The starting coordinates (in pixels) of the animation's first frame within the sprite sheet.
*   **`offset_x`**, **`offset_y`**: Additional offsets applied to the sprite's position when this specific animation is active.
*   **`shrink_by_one_pixel`**: If set to `1`, the sprite's bounding box is reduced by one pixel on each side, useful for fine-tuning hitboxes.
*   **`has_offset`**: Indicates if `offset_x` and `offset_y` are specific to this animation.
*   **`next_animation`**: Specifies which animation should play automatically after this one finishes (e.g., `intro_stand_up` transitions to `stand`).