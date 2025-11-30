---
title: Player Arm Animations (No Item)
category: entities/gfx
---

# Player Arm Animations (No Item)

This file defines the sprite animations for the player's arm when no item is equipped. It's a crucial component for visualizing player actions and states.

## Sprite Attributes

The main `<Sprite>` tag defines the base properties for all animations.

*   **filename**: `data/enemies_gfx/player_arm_no_item.png` - The texture file containing all the animation frames.
*   **offset\_x**: `3` - Horizontal offset for the sprite.
*   **offset\_y**: `15` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation that plays by default.

## RectAnimation Elements

Each `<RectAnimation>` element defines a specific animation sequence. Key attributes for these elements include:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "jump\_up").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **pos\_x**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **pos\_y**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
*   **loop**: If set to `"0"`, the animation will not loop. By default, animations loop.

### Key Animations and Their Properties

| Animation Name       | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Loop | Notes                               |
| :------------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :--- | :---------------------------------- |
| `stand`              | 6           | 12          | 19           | 8              | 0.2        | Yes  | Default idle animation.             |
| `walk`               | 6           | 12          | 19           | 8              | 0.105      | Yes  | Standard walking animation.         |
| `run`                | 6           | 12          | 19           | 8              | 0.105      | Yes  | Running animation.                  |
| `burn`               | 6           | 12          | 19           | 8              | 0.095      | Yes  | Animation for being on fire.        |
| `jump_up`            | 3           | 12          | 19           | 8              | 0.082      | No   | Ascending during a jump.            |
| `jump_fall`          | 3           | 12          | 19           | 8              | 0.082      | No   | Falling during a jump.              |
| `land`               | 3           | 12          | 19           | 8              | 0.075      | No   | Landing animation.                  |
| `fly_idle`           | 4           | 12          | 19           | 8              | 0.09       | Yes  | Idle animation while flying.        |
| `fly_move`           | 4           | 12          | 19           | 8              | 0.12       | Yes  | Moving animation while flying.      |
| `knockback`          | 4           | 12          | 19           | 8              | 0.06       | Yes  | Animation when being hit and pushed. |
| `swim_idle`          | 4           | 12          | 19           | 8              | 0.08       | Yes  | Idle animation while swimming.      |
| `swim_move`          | 5           | 12          | 19           | 8              | 0.11       | Yes  | Moving animation while swimming.    |
| `attack`             | 6           | 12          | 19           | 8              | 0.11       | No   | General attack animation.           |
| `kick`               | 6           | 12          | 19           | 8              | 0.11       | No   | Kick attack animation.              |
| `kick_alt`           | 6           | 12          | 19           | 8              | 0.11       | No   | Alternative kick animation.         |
| `lower_head`         | 3           | 12          | 19           | 8              | 0.05       | No   | Animation for lowering the head.    |
| `raise_head`         | 3           | 12          | 19           | 8              | 0.05       | No   | Animation for raising the head.     |
| `eat`                | 5           | 12          | 19           | 8              | 0.14       | Yes  | Eating animation.                   |
| `crouch`             | 1           | 12          | 19           | 8              | 0.14       | Yes  | Crouching animation.                |
| `walk_backwards`     | 6           | 12          | 19           | 8              | 0.105      | Yes  | Walking backward animation.         |
| `move_item_stash`    | 5           | 12          | 19           | 8              | 0.07       | No   | Animation for stashing an item.     |
| `move_item`          | 4           | 12          | 19           | 8              | 0.09       | No   | Animation for moving an item.       |
| `throw_old`          | 5           | 13          | 20           | 8              | 0.09       | No   | Older throwing animation.           |
| `stand_crouched`     | 6           | 12          | 19           | 8              | 0.095      | Yes  | Standing while crouched.            |
| `walk_crouched`      | 6           | 12          | 19           | 8              | 0.095      | Yes  | Walking while crouched.             |
| `run_crouched`       | 6           | 12          | 19           | 8              | 0.095      | Yes  | Running while crouched.             |
| `walk_backwards_crouched` | 6           | 12          | 19           | 8              | 0.095      | Yes  | Walking backward while crouched.    |
| `kick_crouched`      | 6           | 12          | 19           | 8              | 0.11       | No   | Kick attack while crouched.         |
| `kick_alt_crouched`  | 6           | 12          | 19           | 8              | 0.11       | No   | Alternative kick while crouched.    |
| `throw_crouched`     | 5           | 13          | 20           | 8              | 0.09       | No   | Throwing animation while crouched.  |
| `rise`               | 5           | 13          | 20           | 8              | 0.11       | No   | Animation for rising up.            |
| `throw`              | 6           | 13          | 20           | 8              | 0.09       | No   | Standard throwing animation.        |
| `slide`              | 4           | 12          | 19           | 8              | 0.08       | Yes  | Sliding animation.                  |
| `slide_end`          | 3           | 12          | 19           | 8              | 0.06       | No   | End of slide animation.             |
| `slide_crouched`     | 4           | 12          | 19           | 8              | 0.08       | Yes  | Sliding while crouched.             |
| `slide_end_crouched` | 3           | 12          | 19           | 8              | 0.06       | No   | End of crouched slide animation.    |
| `slide_start`        | 2           | 12          | 19           | 8              | 0.05       | No   | Start of slide animation.           |
| `slide_start_crouched` | 2           | 12          | 19           | 8              | 0.05       | No   | Start of crouched slide animation.  |
| `hurt`               | 3           | 13          | 20           | 8              | 0.08       | No   | Hurt animation (ground).            |
| `hurt_swim`          | 3           | 13          | 20           | 8              | 0.08       | No   | Hurt animation (swimming).          |
| `hurt_fly`           | 3           | 13          | 20           | 8              | 0.08       | No   | Hurt animation (flying).            |
| `grab_item`          | 9           | 12          | 19           | 9              | 0.1        | No   | Animation for grabbing an item.     |
| `idle_hold`          | 6           | 12          | 19           | 8              | 0.24       | Yes  | Idle animation while holding something. |
| `throw_item`         | 10          | 12          | 19           | 10             | 0.07       | No   | Animation for throwing an item.     |
| `push_start`         | 4           | 12          | 19           | 8              | 0.09       | No   | Start of push animation.            |
| `push`               | 6           | 12          | 19           | 8              | 0.12       | Yes  | Pushing animation.                  |

### Animation Events

Some animations can trigger events at specific frames. These are defined within `<Event>` tags nested inside `<RectAnimation>`.

*   **name**: The name of the event (e.g., "step", "land", "throw\_release", "sprite\_invisible", "sprite\_visible").
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance of the event occurring (usually 1 for guaranteed events).
*   **check\_physics\_material**: If set to "0", the event is not dependent on the physics material of the player's current location.
*   **max\_distance**: Maximum distance for certain event types (e.g., sound effects).
*   **on\_finished**: If set to "1", the event triggers when the animation finishes.

**Example Event:**

```xml
<Event
  check_physics_material="0"
  frame="2"
  max_distance="500"
  name="step"
  on_finished="0"
  probability="1">
</Event>
```
This event named "step" occurs on frame 2 of the animation, with a probability of 1, and is not dependent on physics material.