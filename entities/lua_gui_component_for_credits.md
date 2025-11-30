---
title: Lua GUI Component for Credits
category: entities
---

# Lua GUI Component for Credits

This entity defines a Lua component used for managing the game's credits screen. It leverages a Lua script to handle the display and logic of the credits.

## Key Attributes

*   **`script_source_file`**: Specifies the path to the Lua script that controls the component's behavior. In this case, it's `data/scripts/ui/credits.lua`.
*   **`vm_type`**: Determines how the Lua virtual machine is managed. `ONE_PER_COMPONENT_INSTANCE` means each instance of this component gets its own VM.
*   **`enable_coroutines`**: When set to `1`, allows the Lua script to use coroutines for asynchronous operations.
*   **`execute_on_added`**: If `1`, the script's `on_added` function will be called when the entity is added to the game world.
*   **`execute_times`**: Controls how many times the script's `on_update` function is executed. `1` means it will only run once.
*   **`execute_every_n_frame`**: If set to a value other than `-1`, the `on_update` function will execute every `n` frames. `-1` indicates it's not used for frame-based updates in this configuration.

## Lua Script

The core logic for the credits screen is handled by the `data/scripts/ui/credits.lua` file. This script would typically contain functions for:

*   Loading and displaying credit text.
*   Handling scrolling or animation of credits.
*   Managing player input to exit the credits.
*   Potentially triggering other UI elements or game states.

```lua
-- Example snippet from data/scripts/ui/credits.lua (not provided in source)
-- This is illustrative of what the script might contain.

local credits_data = {
    -- ... credit entries ...
}

function on_added(entity)
    -- Initialize credits display
    print("Credits screen loaded!")
    -- ... logic to create and display UI elements ...
end

function on_update(entity, delta_time)
    -- Handle scrolling, input, etc.
    -- For example:
    -- if Input.IsActionPressed("exit") then
    --     Game.ExitCredits()
    -- end
end

function on_removed(entity)
    -- Clean up UI elements
    print("Credits screen removed.")
end
```