---
title: Racing Cart Checkpoint Logic
category: scripts
---

# Racing Cart Checkpoint Logic

This script defines the behavior for a racing cart checkpoint system in Noita. It handles detecting when a cart crosses the finish line or a checkpoint, tracking lap times, and updating best lap records.

## Core Functionality

The primary function `collision_trigger` is responsible for handling all interactions with the checkpoint entity. It determines if the colliding entity is the finish line or a specific checkpoint and updates the internal state accordingly.

### Key Attributes & Elements

*   **`checkpoint_count`**: (Number) Defines the total number of checkpoints in the race.
*   **`EntityHasTag(colliding_id, "finish_line")`**: Detects if the colliding entity is the designated finish line.
*   **`EntityHasTag(colliding_id, "checkpoint_<i>")`**: Detects if the colliding entity is a specific checkpoint (where `<i>` is the checkpoint number).
*   **`get_variable_storage_component(entity_id, name)`**: Retrieves a storage component associated with the checkpoint entity, used to store state like checkpoint completion status and lap times.
*   **`ComponentSetValue2(storage_comp, "value_bool", true)`**: Marks a checkpoint as completed.
*   **`ComponentSetValue2(storage_comp, "value_int", time)`**: Sets integer values, primarily used for storing lap start times and recorded lap times.
*   **`GameGetFrameNum()`**: Gets the current game frame number, used for calculating time differences.
*   **`EntityGetClosestWithTag(pos_x, pos_y, tag)`**: Finds the closest entity with a specific tag, used to locate stopwatch displays.

## Lap Time Calculation

When the finish line is crossed:

1.  **Checkpoint Completion Check**: The script iterates through all checkpoints to determine how many have been completed in the current lap.
2.  **Lap Start Time**: It reads the `lap_start_time` from storage.
3.  **Lap Completion**:
    *   If all checkpoints are completed (`completed >= checkpoint_count`), the lap is considered finished.
    *   The current lap time is calculated as `GameGetFrameNum() - lap_start_time`.
    *   This lap time is then compared against the `best_time` stored in the checkpoint entity.
    *   If the current lap is faster, `best_time` is updated.
    *   The `stopwatch_prev_lap` and `stopwatch_best_lap` entities (if found) are updated with the respective times.
4.  **New Lap Start**: If the finish line is crossed but not all checkpoints were completed, or if a lap was just completed, the `lap_start_time` is reset to the current frame number to begin a new lap.

## Checkpoint Logic

When an entity collides with a checkpoint:

1.  The script checks if the colliding entity has a tag matching a checkpoint (e.g., `"checkpoint_1"`).
2.  If a match is found, it retrieves the corresponding boolean variable from the checkpoint's storage component.
3.  The variable is set to `true`, indicating that this checkpoint has been passed.

```lua
-- Example of how a checkpoint might be marked as completed
local checkpoint_name = "checkpoint_1"
local storage_comp = get_variable_storage_component(entity_id, checkpoint_name)
if storage_comp then
	ComponentSetValue2(storage_comp, "value_bool", true)
end
```