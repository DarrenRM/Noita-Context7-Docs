---
title: Boss Ghost Laser Emitter
category: entities
---

---

# Boss Ghost Laser Emitter

This entity defines the behavior of the lasers emitted by the boss ghost. It dynamically adjusts laser properties based on a stored status value.

## Key Components and Behavior

### VariableStorageComponent (laser_status)

*   **Purpose:** Stores a floating-point value representing the current "status" of the laser. This status influences the laser's damage, length, and radius.
*   **`value_float`:** The primary variable holding the laser status.

### LaserEmitterComponent

*   **Purpose:** Controls the emission of the laser beam.
*   **`is_emitting`:** A boolean that determines if the laser is currently active. This is controlled by the `laser_status`.
*   **`laser` (nested properties):**
    *   **`damage_to_entities`:** The damage dealt by the laser. It's calculated as `0.08 + status * 0.01`.
    *   **`max_length`:** The maximum range of the laser. It's calculated as `8 + status * 8`.
    *   **`beam_radius`:** The width of the laser beam. It's calculated as `3 + status * 0.1`.

## Script Logic

The `lasers.lua` script handles the dynamic updates for the boss ghost's lasers.

1.  **Initialization:**
    *   Retrieves the entity's current transform (position and angle).
    *   Sets the entity's angle to rotate based on the game frame number, creating a spinning effect.

2.  **Status Update:**
    *   Checks for the `laser_status` VariableStorageComponent.
    *   If found, it reads the current `value_float` (status).
    *   **Emission Control:**
        *   If `status <= 0`, `is_emitting` is set to `false` for all `LaserEmitterComponent`s.
        *   Otherwise, `is_emitting` is set to `true`.
    *   **Laser Property Adjustment:**
        *   The `damage_to_entities`, `max_length`, and `beam_radius` of the `LaserEmitterComponent` are dynamically updated based on the current `status`.
    *   **Status Decay:**
        *   The `status` is decremented by `0.02` each frame, with a minimum value of `0`.
        *   The updated `status` is written back to the `value_float` of the `VariableStorageComponent`.

## Key Attributes for Modding

*   **`damage_to_entities`:** Modifiable to change the laser's damage output.
*   **`max_length`:** Modifiable to alter the laser's range.
*   **`beam_radius`:** Modifiable to change the laser's thickness.
*   **`value_float` (in `laser_status` VariableStorageComponent):** The core variable to manipulate for controlling laser intensity and duration.
*   **Status Decay Rate (`0.02`):** The rate at which the laser's power diminishes over time.