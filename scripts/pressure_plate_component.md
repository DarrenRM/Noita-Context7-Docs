---
title: Pressure Plate Component
category: scripts
---

# Pressure Plate Component

This documentation describes the functionality and usage of the `pressure_plate` script in Noita, focusing on its role in triggering events, particularly for temple doors.

## Core Functionality

The `pressure_plate` script is designed to detect when a player or object interacts with it, triggering a subsequent action. The primary example provided demonstrates how it can be used to open or close temple doors by manipulating their physics joints.

## Key Functions

### `Component_SetTimeOut( entity_id, frames, script_file )`

This utility function adds a `LuaComponent` to an entity that will execute a specified script after a given number of frames. It's used here to ensure that the temple door's physics state is reset after a period.

*   **`entity_id`**: The ID of the entity to attach the timeout component to.
*   **`frames`**: The number of game frames to wait before executing the script.
*   **`script_file`**: The path to the Lua script to execute.

### `pressure_plate_change( new_state )`

This function is the main logic for the pressure plate. It's called when the plate's state changes (e.g., when stepped on).

1.  **Finds the Temple Door**: It identifies the closest entity with the tag "temple_door" relative to the pressure plate's position.
2.  **Modifies Physics**: If a temple door is found, it iterates through all `PhysicsJointComponent`s attached to it.
    *   It adjusts the `delta_y` property of the joint based on the `new_state` to simulate opening or closing.
3.  **Sets Timeout**: It then calls `Component_SetTimeOut` to schedule the execution of `physics_stopmousejoint.lua` after 5 minutes (300 frames), likely to revert the door's physics state.

## Example Usage (Temple Door Interaction)

The provided script snippet demonstrates a common use case:

```lua
-- Assuming this is part of a pressure plate entity's script
function MyPressurePlateScript( entity_id )
    -- ... logic to detect player interaction ...

    if player_stepped_on_plate then
        pressure_plate_change( 1 ) -- Trigger door to open
    elseif player_stepped_off_plate then
        pressure_plate_change( 0 ) -- Trigger door to close
    end
end
```

## Key Attributes/Elements Involved

*   **`LuaComponent`**: Used to attach custom Lua scripting logic to entities.
*   **`EntityAddComponent`**: Function to add components to an entity.
*   **`ComponentSetValue`**: Function to set values for component properties.
*   **`GameGetFrameNum`**: Returns the current game frame number.
*   **`EntityGetTransform`**: Retrieves the position of an entity.
*   **`EntityGetClosestWithTag`**: Finds the nearest entity with a specific tag.
*   **`PhysicsJointComponent`**: A component that manages physics joints, used here to control the temple door's movement.
*   **`edit_all_components`**: A utility function to apply a modification to all components of a specific type on an entity.
*   **`vars.delta_y`**: A property within `PhysicsJointComponent` that likely controls the vertical displacement of the joint.

## Summary

The `pressure_plate.lua` script provides a foundational mechanism for creating interactive elements in Noita. Its primary example showcases how to leverage entity components and scripting to create dynamic environmental effects, such as animated temple doors, by manipulating physics and scheduling timed events.