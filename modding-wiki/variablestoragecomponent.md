---
title: VariableStorageComponent
source: https://noita.wiki.gg/wiki/Documentation:VariableStorageComponent
category: modding-wiki
---

# VariableStorageComponent

This documentation covers the `VariableStorageComponent` in Noita, a crucial component for managing and storing custom variables associated with entities. Understanding and utilizing this component is essential for creating complex mods that require persistent data or dynamic behavior tied to specific game objects.

## Overview

The `VariableStorageComponent` allows modders to attach arbitrary key-value pairs to entities. These variables can be of various types (integers, floats, strings, booleans, etc.) and can be accessed and modified through Lua scripting. This is fundamental for implementing custom mechanics, tracking entity states, or creating unique interactions within your mods.

## Component Definition

The `VariableStorageComponent` is defined within an entity's XML file. It doesn't have any specific parameters that need to be configured directly within the XML for basic usage. Its primary function is to provide a storage mechanism that can be populated and accessed via Lua.

```xml
<entity name="my_custom_entity">
    <VariableStorageComponent />
    <!-- Other components -->
</entity>
```

## Lua API for VariableStorageComponent

The `VariableStorageComponent` is primarily interacted with through Lua scripting. The following functions are available for managing variables:

### Getting Variables

*   **`entity:get_variable(variable_name)`**: Retrieves the value of a variable associated with the entity. Returns `nil` if the variable does not exist.

### Setting Variables

*   **`entity:set_variable(variable_name, value)`**: Sets or updates the value of a variable associated with the entity. The `value` can be of various Lua types (number, string, boolean, table).

### Checking for Variables

*   **`entity:has_variable(variable_name)`**: Returns `true` if the entity has a variable with the given name, `false` otherwise.

### Removing Variables

*   **`entity:remove_variable(variable_name)`**: Removes a variable from the entity.

## Examples

Here are some common use cases and how to implement them with `VariableStorageComponent`:

### Example 1: Storing a Custom Health Value

This example shows how to store and modify a custom health value for an entity.

```lua
-- Get the entity (assuming you have a reference to it)
local my_entity = ... -- Replace with how you get your entity reference

-- Initialize custom health if it doesn't exist
if not my_entity:has_variable("custom_health") then
    my_entity:set_variable("custom_health", 100)
end

-- Function to take damage
function take_custom_damage(entity, damage_amount)
    local current_health = entity:get_variable("custom_health")
    if current_health then
        current_health = current_health - damage_amount
        entity:set_variable("custom_health", current_health)
        print("Entity health is now: " .. current_health)
        if current_health <= 0 then
            print("Entity defeated!")
            -- Add logic for entity death here
        end
    end
end

-- Example usage:
take_custom_damage(my_entity, 25)
```

### Example 2: Tracking Player State

This example demonstrates how to track a custom state for the player, such as whether they have collected a specific item.

```lua
-- Assuming 'player' is a reference to the player entity
local player = ...

-- When the player collects the item:
player:set_variable("has_special_item", true)
print("Player collected the special item!")

-- Later, to check if the player has the item:
if player:has_variable("has_special_item") and player:get_variable("has_special_item") then
    print("Player can now use the special ability.")
    -- Enable special ability
else
    print("Player does not have the special item.")
end
```

### Example 3: Storing Entity-Specific Data

This example shows storing a string value, perhaps a unique identifier or a descriptive tag.

```lua
-- Get an entity
local some_entity = ...

-- Assign a unique identifier
some_entity:set_variable("unique_id", "quest_giver_001")

-- Retrieve and use the identifier
local entity_id = some_entity:get_variable("unique_id")
if entity_id == "quest_giver_001" then
    print("This is the main quest giver.")
    -- Start quest logic
end
```

## Important Considerations

*   **Variable Naming:** Use descriptive and consistent names for your variables to avoid conflicts and improve readability. Prefixing variables with your mod's name is a good practice (e.g., `my_mod_custom_value`).
*   **Data Types:** While `VariableStorageComponent` is flexible, be mindful of the data types you are storing. Lua's dynamic typing handles most common types, but complex nested tables might require careful handling.
*   **Persistence:** Variables stored with `VariableStorageComponent` are generally persistent within a game session. However, they are not saved between game sessions by default. For save-game persistence, you would need to implement custom saving/loading logic, potentially by serializing these variables into a save file.
*   **Performance:** While generally efficient, avoid creating and destroying a massive number of variables on frequently updated entities in performance-critical loops.

## Related Components and Concepts

*   **Entity XML:** Understanding how to define entities and their components is fundamental.
*   **Lua Scripting:** The primary interface for interacting with `VariableStorageComponent`. Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for more general Lua functions.
*   **Custom Components:** For more complex data management or behavior, you might consider creating your own custom components.

By mastering the `VariableStorageComponent`, you unlock a powerful tool for creating dynamic and data-driven mods in Noita.