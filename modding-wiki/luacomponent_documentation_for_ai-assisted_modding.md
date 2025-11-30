---
title: LuaComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:LuaComponent
category: modding-wiki
---

# LuaComponent Documentation

This document provides essential information about the `LuaComponent` in Noita, a fundamental element for modding the game's behavior through Lua scripting. Understanding `LuaComponent` is crucial for creating custom game mechanics, modifying existing ones, and integrating complex logic into your Noita mods.

## Understanding LuaComponent

The `LuaComponent` is the primary mechanism for attaching custom Lua scripts to game entities in Noita. It allows modders to define and execute specific behaviors, reactions, and logic for objects within the game world. This component acts as a bridge between the game's entity system and the powerful scripting capabilities of Lua.

### Core Concepts

*   **Entity-Component System:** Noita uses an entity-component system. Entities are game objects, and components are data or functionality attached to them. `LuaComponent` is one such component.
*   **Script Execution:** When an entity with a `LuaComponent` is active in the game, its associated Lua script is executed according to predefined events or conditions.
*   **Modding Power:** This component is the backbone of most complex Noita mods, enabling everything from simple item effects to intricate new game systems.

### Essential Functions and Events

The `LuaComponent` relies on specific functions and event handlers within your Lua scripts to interact with the game. These functions are called by the game engine at appropriate times.

#### Initialization (`Init`)

This function is called once when the entity is first loaded or spawned. It's the ideal place for setting up initial variables, registering event callbacks, or performing any one-time setup.

```lua
function Init(entity, component_name)
    -- Your initialization code here
    print("LuaComponent initialized for entity: " .. entity.id)
end
```

#### Update (`Update`)

This function is called every frame for active entities. It's used for continuous logic, such as movement, AI behavior, or checking conditions that need to be evaluated constantly.

```lua
function Update(entity, component_name)
    -- Your update code here
    -- Example: Make the entity slowly rotate
    local transform = entity.transform
    if transform then
        transform.rotation = transform.rotation + 0.5 * Game.GetDeltaTime()
    end
end
```

#### Custom Event Handlers

You can define custom functions that are called when specific game events occur. These events are often triggered by other components or game systems.

```lua
function OnCollision(entity, component_name, other_entity)
    print("Collision detected with: " .. other_entity.id)
    -- Example: Destroy the entity on collision
    entity.Destroy()
end
```

### Accessing Entity Data

Within your Lua script, you can access and modify various properties of the entity and its components.

*   **Entity ID:** `entity.id`
*   **Transform:** `entity.transform` (contains position, rotation, scale)
*   **Components:** You can access other components attached to the entity using their names, e.g., `entity.GetComponent("Sprite")`.

### Example `LuaComponent` XML Definition

A `LuaComponent` is typically defined in an entity's XML file.

```xml
<Entity name="my_custom_entity">
    <LuaComponent
        script_path="data/scripts/my_custom_script.lua"
        is_active="true"
    />
    <!-- Other components -->
</Entity>
```

*   `script_path`: The relative path to your Lua script file.
*   `is_active`: Whether the component should be active by default.

## Advanced Usage and Best Practices

### Event Registration

To make your custom event handlers work, you often need to register them with the game's event system. This is typically done within the `Init` function.

```lua
function Init(entity, component_name)
    -- Register for collision events
    entity.RegisterComponent(component_name, "OnCollision")

    -- Register for a custom event (if you define one elsewhere)
    -- entity.RegisterComponent(component_name, "MyCustomEvent")
end
```

### Game API Access

The `LuaComponent` has access to a wide range of game functions and data through the Noita Lua API.

*   **Global Functions:** `Game.GetWorld()`, `Game.GetPlayer()`, `Game.SpawnEntity()`, etc.
*   **Entity Manipulation:** `entity.SetPosition()`, `entity.AddComponent()`, `entity.RemoveComponent()`, `entity.Destroy()`.

Refer to the [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API) for a comprehensive list of available functions.

### Performance Considerations

*   **Avoid Heavy Computations in `Update`:** If you have complex calculations, try to perform them less frequently or optimize them.
*   **Unregister Events:** When an entity is destroyed or its `LuaComponent` is deactivated, ensure you unregister any event handlers to prevent memory leaks or unexpected behavior.

### Debugging

*   **`print()` Statements:** Use `print()` extensively in your Lua scripts. The output will appear in the game's console (accessible via the debug console in-game).
*   **Error Handling:** Implement `pcall` for functions that might fail to catch errors gracefully.

```lua
function Update(entity, component_name)
    local success, result = pcall(function()
        -- Potentially error-prone code
        return 1 / 0
    end)

    if not success then
        print("Error in Update: " .. result)
    end
end
```

## Common Pitfalls

*   **Incorrect `script_path`:** Ensure the path to your Lua script is correct relative to the `data` folder.
*   **Forgetting Event Registration:** Custom event handlers won't be called if they aren't registered.
*   **Modifying Game State Incorrectly:** Be careful when modifying core game mechanics, as it can lead to instability. Always back up your saves.
*   **Infinite Loops:** Ensure your `Update` functions have exit conditions or don't run indefinitely.

By mastering the `LuaComponent`, you unlock the full potential of Noita modding, allowing you to create truly unique and engaging experiences.