---
title: Player Halo Movement Script
category: scripts
---

---

# Player Halo Movement Script

This script controls the movement and bobbing behavior of a player's halo entity in Noita. It's designed to make the halo follow the player with a slight offset and a subtle bobbing motion.

## Key Attributes

*   **`offset_y`**: Determines the vertical offset of the halo from the player's center.
*   **`follow_amount`**: Controls how quickly the halo moves towards the player's target position. A higher value means faster, more direct following.
*   **`bob_amount`**: The amplitude of the vertical bobbing motion.
*   **`bob_speed`**: The speed at which the halo bobs up and down.
*   **`roll_amount`**: The amplitude of the rotational swaying motion.
*   **`roll_speed`**: The speed at which the halo sways rotationally.

## Core Logic

The script calculates the halo's position based on the player's root entity's transform. It then applies:

1.  **Vertical Offset**: Adjusts the target Y position by `offset_y`.
2.  **Bobbing Motion**: Uses `math.sin` with the frame number (`t`) and `bob_speed` to create a smooth up-and-down movement, scaled by `bob_amount`.
3.  **Rolling Motion**: Similar to bobbing, `math.sin` is used with `t` and `roll_speed` to create a rotational sway, scaled by `roll_amount`.
4.  **Interpolation**: The `vec_lerp` function smoothly moves the halo's current position (`x`, `y`) towards the calculated `target_x`, `target_y` based on `follow_amount`.
5.  **Transform Update**: Finally, `EntitySetTransform` updates the halo's position and rotation.