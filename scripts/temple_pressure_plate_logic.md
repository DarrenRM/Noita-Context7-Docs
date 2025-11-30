---
title: Temple Pressure Plate Logic
category: scripts
---

# Temple Pressure Plate Logic

This script defines the behavior for a pressure plate in the temple area, specifically its interaction with temple doors. When the pressure plate's state changes, it attempts to find the closest entity tagged as "temple_door" and modifies its `PhysicsJointComponent` to enable or disable its motor.

## Key Functionality

### `pressure_plate_change( new_state )`

This function is the core logic for the pressure plate. It's designed to be called when the plate's state changes (e.g., when an entity steps on or off it).

*   **`new_state`**: An integer representing the new state of the pressure plate.
    *   `1`: Typically signifies the plate is activated (e.g., something is on it).
    *   `0`: Typically signifies the plate is deactivated (e.g., nothing is on it).

#### Internal Logic:

1.  **Get Entity Information**: Retrieves the `entity_id` and its `pos_x`, `pos_y` coordinates for the pressure plate itself.
2.  **Find Temple Door**: Uses `EntityGetClosestWithTag` to locate the nearest entity with the tag `"temple_door"`.
3.  **Modify Door Physics**: If a temple door is found:
    *   It iterates through all `PhysicsJointComponent` components attached to the temple door.
    *   Based on the `new_state`:
        *   If `new_state` is `1`, it sets `mMotorEnabled` to `1`, effectively enabling the door's movement mechanism.
        *   If `new_state` is `0`, it sets `mMotorEnabled` to `0`, disabling the door's movement mechanism.

## Relevant Components and Attributes

### `PhysicsJointComponent`

This component is crucial for the temple door's functionality. The script directly manipulates its `mMotorEnabled` attribute.

*   **`mMotorEnabled`**: A boolean-like integer (`1` for enabled, `0` for disabled) that controls whether the joint's motor is active.

## Example Usage (Conceptual)

While the provided code snippet focuses on the `pressure_plate_change` function, a typical setup would involve:

1.  An entity representing the pressure plate with a `LuaComponent` that calls `pressure_plate_change` when its state is updated.
2.  An entity representing the temple door with a `PhysicsJointComponent` and the tag `"temple_door"`.

```lua
-- Example of how pressure_plate_change might be called (not part of the provided snippet)
-- Assuming 'pressure_plate_entity_id' is the ID of the pressure plate entity
-- and 'is_activated' is a boolean indicating its state

local current_state = is_activated and 1 or 0
pressure_plate_change(current_state)
```