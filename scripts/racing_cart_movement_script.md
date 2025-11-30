---
title: Racing Cart Movement Script
category: scripts
---

# Racing Cart Movement Script

This script governs the movement and behavior of the racing cart entity in Noita. It handles player input for thrust, collision detection, lap time tracking, and visual updates.

## Key Functionality

### Movement and Input

*   **Thrust Control:** The cart accelerates forward when the player holds the "fly" button (typically mapped to jump or a dedicated fly key). The `speed` variable determines the base acceleration.
*   **Directional Movement:** The cart's movement direction is dictated by the player's wand orientation. The `dir` variable captures this.
*   **Velocity Update:** The script integrates player thrust with the cart's existing velocity using `vec_add`.

### Collision and Stuck Detection

*   **Wall Detection:** `RaytracePlatforms` is used to check for collisions with platforms in front of the cart.
*   **Stuck Release:** If the cart is detected as stuck in a wall, the script attempts to reposition it slightly to free it. It iterates through several potential positions around the cart.

### Lap Time Tracking

*   **Stopwatch Integration:** The script interacts with a separate "stopwatch" entity (identified by the "stopwatch\_lap" tag).
*   **Lap Start Time:** It stores the frame number when a lap begins using a `VariableStorageComponent` named "lap\_start\_time".
*   **Lap Time Calculation:** The current lap time is calculated by subtracting the `lap_start_time` from the current `GameGetFrameNum()`. This value is then updated in the stopwatch entity.

### Visual Updates

*   **Sprite Animation:** The `SpriteComponent` is updated to change the animation based on whether the player is thrusting (`fly` vs. `float`).
*   **Sprite Flipping:** The `special_scale_y` property of the `SpriteComponent` is used to flip the sprite vertically if the cart is facing backward (indicated by `dir`).
*   **Jetpack Activation:** The "jetpack" component is enabled or disabled based on player input.

## Key Attributes and Components

| Attribute/Component        | Description