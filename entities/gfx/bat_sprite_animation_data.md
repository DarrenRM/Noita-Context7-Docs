---
title: Bat Sprite Animation Data
category: entities/gfx
---

# Bat Sprite Animation Data

This document details the sprite animation data for the "bat" enemy in Noita, focusing on its graphical representation and animation states.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/bat.png` - The path to the sprite sheet image.
*   **`offset_x`**: `8` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `12` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `"stand"` - The animation state that plays by default.

## Animation States

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation state for the bat.

### Common Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation state (e.g., "stand", "walk", "burn").
*   **`frame_count`**: `6` - The total number of frames in this animation.
*   **`frame_width`**: `17` - The width of each individual frame in pixels.
*   **`frame_height`**: `17` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `6` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: `0` - The X-coordinate of the top-left corner of the animation frame area within the sprite sheet.
*   **`pos_y`**: `1` - The Y-coordinate of the top-left corner of the animation frame area within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - Indicates if frames should be shrunk by one pixel (likely for visual adjustment).

### Defined Animation States:

| Name       | Description                               |
| :--------- | :---------------------------------------- |
| `stand`    | The bat's idle standing animation.        |
| `walk`     | Animation for when the bat is walking.    |
| `run`      | Animation for when the bat is running.    |
| `burn`     | Animation played when the bat is burning. |
| `fly_idle` | The bat's idle flying animation.          |
| `fly_move` | Animation for when the bat is flying.     |

## Animation Events

Each `<RectAnimation>` can contain `<Event>` tags, which trigger specific actions at certain frames.

### Common Attributes for `Event`:

*   **`frame`**: The frame number (1-indexed) at which the event occurs.
*   **`name`**: The name of the event to trigger (e.g., "flap").
*   **`probability`**: `1` - The chance (100%) that this event will trigger when the specified frame is reached.
*   **`on_finished`**: `0` - Indicates if the event should only trigger once the animation finishes. `0` means it triggers immediately.
*   **`max_distance`**: `500` - A condition for the event, possibly related to distance.
*   **`check_physics_material`**: `0` - Whether to check physics materials for the event.

### Bat-Specific Events:

All defined animation states for the bat include a single event:

*   **`name`**: `"flap"`
*   **`frame`**: `1`
*   **`probability`**: `1`

This suggests that a "flap" sound or visual effect is intended to be triggered on the first frame of every animation state.