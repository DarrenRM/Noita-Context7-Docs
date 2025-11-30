---
title: Boss Meat Body Sprite
category: entities
---

# Boss Meat Body Sprite

This document describes the sprite data for the "Boss Meat" entity's body in Noita. It defines the visual appearance and animations associated with this entity.

## Sprite Definition

The primary sprite for the boss meat body is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/entities/animals/boss_meat/body.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `24` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `24` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `"stand"` - The animation that plays by default when the entity is idle.

## Animations

The sprite supports several distinct animations, each defined by a `<RectAnimation>` tag.

### `stand` Animation

This is the default idle animation.

*   **`name`**: `"stand"`
*   **`pos_x`**: `0`
*   **`pos_y`**: `0`
*   **`frame_count`**: `1` - Number of frames in this animation.
*   **`frame_width`**: `48` - Width of each animation frame.
*   **`frame_height`**: `48` - Height of each animation frame.
*   **`frame_wait`**: `0.12` - Time in seconds to wait between frames.
*   **`frames_per_row`**: `12` - How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: `1` - Indicates that the animation should loop.

### `open` Animation

This animation likely represents the boss meat opening up.

*   **`name`**: `"open"`
*   **`pos_x`**: `0`
*   **`pos_y`**: `48` - Starts at Y-coordinate 48 in the sprite sheet.
*   **`frame_count`**: `4`
*   **`frame_width`**: `48`
*   **`frame_height`**: `48`
*   **`frame_wait`**: `0.09`
*   **`frames_per_row`**: `4`
*   **`next_animation`**: `"opened"` - Transitions to the "opened" animation after completion.
*   **`loop`**: `0` - This animation does not loop.

### `opened` Animation

This animation likely represents the boss meat in an open state.

*   **`name`**: `"opened"`
*   **`pos_x`**: `0`
*   **`pos_y`**: `96` - Starts at Y-coordinate 96 in the sprite sheet.
*   **`frame_count`**: `1`
*   **`frame_width`**: `48`
*   **`frame_height`**: `48`
*   **`frame_wait`**: `0.12`
*   **`frames_per_row`**: `4`
*   **`loop`**: `1` - This animation loops.

### `close` Animation

This animation likely represents the boss meat closing.

*   **`name`**: `"close"`
*   **`pos_x`**: `0`
*   **`pos_y`**: `144` - Starts at Y-coordinate 144 in the sprite sheet.
*   **`frame_count`**: `4`
*   **`frame_width`**: `48`
*   **`frame_height`**: `48`
*   **`frame_wait`**: `0.09`
*   **`frames_per_row`**: `4`
*   **`next_animation`**: `"stand"` - Transitions back to the "stand" animation after completion.
*   **`loop`**: `0` - This animation does not loop.