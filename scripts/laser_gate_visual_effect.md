---
title: Laser Gate Visual Effect
category: scripts
---

# Laser Gate Visual Effect

This script controls the visual pulsing effect of a laser gate, making it appear to flicker on and off.

## Core Functionality

The script dynamically adjusts the `is_emitting` property of the `LaserEmitterComponent` based on a calculated "arc" value. This creates a visual pulsing or flickering effect.

### Key Components and Attributes

*   **`LaserEmitterComponent`**: This is the primary component targeted by the script. It's responsible for the laser emission itself.
    *   **`is_emitting`**: A boolean value that determines if the laser is currently active. The script toggles this between `true` and `false`.

### Logic Breakdown

1.  **Get Entity and Transform**: The script first retrieves the current entity's ID and its position (`x`, `y`).
2.  **Calculate Arc Value**: A value named `arc` is calculated using a cosine function. This function incorporates:
    *   `GameGetFrameNum()`: The current game frame number, providing a time-based oscillation.
    *   `x * 0.05`: The entity's X-coordinate, adding spatial variation to the oscillation.
    *   `x * 0.05`: The entity's Y-coordinate, adding spatial variation to the oscillation.
    *   The result of `math.cos()` will oscillate between -1 and 1.
3.  **Conditional Emission**:
    *   If the calculated `arc` value is less than 0 (meaning the cosine wave is in its negative phase), the `is_emitting` property of the `LaserEmitterComponent` is set to `true`.
    *   Otherwise (if `arc` is 0 or positive), `is_emitting` is set to `false`.

This creates a continuous, frame-by-frame pulsing effect for the laser gate.