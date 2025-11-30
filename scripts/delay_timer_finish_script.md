---
title: Delay Timer Finish Script
category: scripts
---

---

# Delay Timer Finish Script

This script is designed to be attached to an entity that acts as a timer. When the timer finishes, it triggers a specific event defined in `event_list.lua`.

## Purpose

The primary function of this script is to execute a delayed action associated with a specific event ID. This is useful for creating timed sequences or events in Noita.

## Key Components

### Entity Setup

*   **`VariableStorageComponent`**: This component is crucial. It must contain a variable named `"event"` with a `value_string` that corresponds to an `id` defined in `streaming_events`.

### Event Handling

*   **`streaming_events`**: This global table (defined in `data/scripts/streaming_integration/event_list.lua`) holds the definitions for various streaming events.
*   **`event_id`**: The script retrieves the `event_id` from the entity's `VariableStorageComponent`.
*   **`action_delayed`**: If an event in `streaming_events` has a function assigned to its `action_delayed` field, that function will be executed.

## Usage Example

1.  **Create an Entity**: Add an entity in your mod.
2.  **Attach Components**:
    *   Add a `VariableStorageComponent`.
    *   Inside `VariableStorageComponent`, add a variable named `"event"` of type `string`.
    *   Set the `value_string` of this variable to the `id` of a desired event from `streaming_events` (e.g., `"my_custom_event"`).
3.  **Attach Script**: Attach this `delay_timer_finish.lua` script to the same entity.
4.  **Define Event**: Ensure you have a corresponding entry in `data/scripts/streaming_integration/event_list.lua` with an `id` matching the `value_string` you set, and define the `action_delayed` function for that event.

```lua
-- Example entry in streaming_events (in event_list.lua)
streaming_events = {
    -- ... other events
    {
        id = "my_custom_event",
        action_delayed = function(data)
            print("My custom event has finished its delay!")
            -- Add your custom logic here, e.g., spawn an item, play a sound, etc.
        end,
    },
    -- ... other events
}
```

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/streaming_integration/event_list.lua`