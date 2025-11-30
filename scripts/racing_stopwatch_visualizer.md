---
title: Racing Stopwatch Visualizer
category: scripts
---

---

# Racing Stopwatch Visualizer

This script defines the visual representation of the Racing Stopwatch entity in Noita. It reads a time value (stored as frames) from the `VariableStorageComponent` and displays it using a series of sprites arranged in rings and a central indicator.

## Key Components and Logic

### Time Reading and Conversion

*   **`frames`**: Reads an integer value representing elapsed frames from the `VariableStorageComponent`. This value is assumed to be updated by `racing_cart_checkpoint.lua`.
*   **`frames_max`**: Defines the maximum possible displayable time, calculated to prevent overflow.
*   **`frames = math.min(frames, frames_max)`**: Clamps the `frames` value to the maximum.
*   **`seconds = frames / 60`**: Converts the frame count into seconds.
*   **`tenths = (seconds % 1) * 10`**: Calculates the tenths of a second for display.

### Visual Elements and Sprites

The script uses three different sprite types to represent different time thresholds:

*   `sprite_big`: `"data/particles/radar_enemy_strong.png"` (Used for seconds >= 30)
*   `sprite_medium`: `"data/particles/radar_enemy_medium.png"` (Used for seconds >= 20 and for the medium ring)
*   `sprite_small`: `"data/particles/radar_enemy_faint.png"` (Used for seconds >= 10 and for the small ring)

### `draw_ring` Function

This helper function draws a ring of sprites around a central point.

*   **`value`**: The numerical value determining how many sprites to draw in the ring.
*   **`radius`**: The radial distance of the ring from the center.
*   **`sprite`**: The sprite to use for the ring segments.

The function iterates 10 times, drawing a sprite if the `value` is greater than or equal to the current segment index. It uses `vec_rotate` to position each sprite in a circular pattern.

### Central Time Display Logic

The script draws a central indicator based on the `seconds` value:

*   **`if seconds >= 30`**: Draws `sprite_big` at the center.
*   **`elseif seconds >= 20`**: Draws `sprite_medium` at the center.
*   **`elseif seconds >= 10`**: Draws `sprite_small` at the center.

### Ring Display Logic

Two rings are drawn to provide a more granular time display:

*   **`draw_ring(seconds % 10, 6, sprite_medium)`**: Draws a ring representing the units digit of seconds (0-9) using `sprite_medium` at a radius of 6.
*   **`draw_ring(tenths, 10, sprite_small)`**: Draws a ring representing the tenths of a second (0-9) using `sprite_small` at a radius of 10.