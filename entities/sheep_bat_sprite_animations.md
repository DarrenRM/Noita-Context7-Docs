---
title: Sheep Bat Sprite Animations
category: entities
---

# Sheep Bat Sprite Animations

This document details the sprite animations for the Sheep Bat enemy in Noita, as defined in `sheep_bat.xml`. It focuses on key attributes for modding purposes.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **`filename`**: `data/enemies_gfx/sheep_bat.png` - The path to the sprite sheet.
*   **`default_animation`**: `walk` - The animation played by default.
*   **`offset_x`**: `10` - Horizontal offset for the sprite.
*   **`offset_y`**: `12` - Vertical offset for the sprite.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Key Attributes for `RectAnimation`:

*   **`name`**: The identifier for the animation (e.g., `fly_idle`, `walk`, `jump_up`).
*   **`frame_count`**: Total number of frames in the animation.
*   **`frame_width`**: Width of each individual frame.
*   **`frame_height`**: Height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
*   **`frame_wait`**: Duration (in seconds) each frame is displayed.
*   **`pos_x`**: X-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **`pos_y`**: Y-coordinate of the top-left corner of the animation frames on the sprite sheet.
*   **`shrink_by_one_pixel`**: If `1`, each frame is shrunk by one pixel.
*   **`has_offset`**: If `1`, the `offset_x` and `offset_y` defined within this tag are used instead of the parent sprite's offsets.

### Notable Animations and Events:

#### `fly_idle` and `fly_move`

These animations are used for flying states.

*   **`frame_count`**: 8
*   **`frame_height`**: 21
*   **`frame_width`**: 21
*   **`frame_wait`**: 0.1
*   **`frames_per_row`**: 8
*   **`pos_y`**: 1
*   **Events**: Trigger a `flap` event on frames 3 and 6.

#### `stand`, `jump_up`, `fall_down`

These animations are for ground-based actions.

*   **`frame_count`**: 4
*   **`frame_height`**: 22
*   **`frame_width`**: 22
*   **`frame_wait`**: 0.23
*   **`frames_per_row`**: 6
*   **`pos_y`**: 22
*   **`has_offset`**: 1 (uses specific offsets for these animations)

#### `walk` and `run`

These animations are for movement on the ground.

*   **`frame_count`**: 6
*   **`frame_height`**: 22
*   **`frame_width`**: 22
*   **`frame_wait`**: 0.12
*   **`frames_per_row`**: 6
*   **`pos_y`**: 44
*   **`has_offset`**: 1
*   **Events**: Trigger a `step` event on frames 2 and 5. The `check_physics_material` attribute is set to `1`, meaning the event might be tied to ground contact.

#### `burn`

This animation is for when the Sheep Bat is burning.

*   **`frame_count`**: 6
*   **`frame_height`**: 22
*   **`frame_width`**: 22
*   **`frame_wait`**: 0.12
*   **`frames_per_row`**: 6
*   **`pos_y`**: 44
*   **`has_offset`**: 1
*   **Events**: Triggers `step` events, similar to `walk` and `run`.

### Event Definitions

Events within animations can trigger specific game actions or sounds.

#### Key Attributes for `Event`:

*   **`name`**: The name of the event (e.g., `flap`, `step`).
*   **`frame`**: The frame number on which the event occurs.
*   **`probability`**: The chance (0 to 1) that the event will trigger.
*   **`on_finished`**: If `1`, the event triggers when the animation finishes.
*   **`check_physics_material`**: If `1`, the event might be conditional on the physics material of the entity or its surroundings.
*   **`max_distance`**: Maximum distance for the event to be considered.

---