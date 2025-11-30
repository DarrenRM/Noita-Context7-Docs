---
title: Wisp Movement Logic
category: entities
---

---

# Wisp Movement Logic

This script defines the movement behavior for a "wisp" entity in Noita, typically a companion or projectile that follows a parent entity. It implements a bobbing motion and lerps towards a dynamically calculated target position.

## Key Attributes and Behaviors

*   **Lerp Amount (`lerp_amount`):** Controls how smoothly the wisp moves towards its target. A value closer to 1 means faster, more direct movement. This is randomized slightly per wisp.
*   **Bobbing Amplitude (`bob_h`, `bob_w`):** Defines the vertical (`bob_h`) and horizontal (`bob_w`) extent of the wisp's bobbing motion.
*   **Bobbing Speed (`bob_speed_y`, `bob_speed_x`):** Determines the speed of the vertical and horizontal bobbing. These are also randomized slightly.
*   **Target Calculation:** The wisp targets a position relative to its parent entity. It attempts to stay slightly above and then applies the bobbing motion to this target.
*   **Movement Interpolation:** Uses `vec_lerp` to smoothly move the wisp's current position towards the calculated target position.
*   **Animation State:** Dynamically switches between "float" and "fly" animations based on the wisp's horizontal distance to its target. It also selects the correct animation direction (left/right) based on its movement.

## Script Logic Breakdown

1.  **Initialization:**
    *   Retrieves the entity's ID and its root entity.
    *   Gets the initial position of the wisp. If it's at (0,0), it uses the parent's position.

2.  **Target Position Calculation:**
    *   Fetches the parent entity's transform.
    *   Sets the initial target Y position to be slightly above the parent (`target_y - 10`).
    *   Calculates a random offset (`r`) based on the entity ID for slight variation.
    *   Randomizes `time`, `bob_speed_y`, `bob_speed_x`, and `lerp_amount` using the random offset to ensure wisps don't move identically.
    *   Applies the bobbing motion to the `target_y` and `target_x` using `math.sin` with the randomized speeds and time.

3.  **Movement:**
    *   Calculates the horizontal distance (`dist_x`) between the wisp and its target.
    *   Uses `vec_lerp` to interpolate the wisp's current position (`pos_x`, `pos_y`) towards the calculated `target_x`, `target_y` using the `lerp_amount`.
    *   Updates the wisp's transform with the new interpolated position.

4.  **Animation Update:**
    *   Accesses the `SpriteComponent` of the wisp.
    *   Determines the animation mode ("float_" or "fly_") based on whether the absolute horizontal distance (`dist_x`) is greater than 28.
    *   Compares the current animation with the required animation mode and direction (left/right).
    *   If the animation needs to change, it updates the `rect_animation` property of the `SpriteComponent`.