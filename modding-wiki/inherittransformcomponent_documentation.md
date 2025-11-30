---
title: InheritTransformComponent Documentation
source: https://noita.wiki.gg/wiki/Documentation:InheritTransformComponent
category: modding-wiki
---

# InheritTransformComponent Documentation

This documentation covers the `InheritTransformComponent` in Noita, a crucial component for understanding how entities inherit transformations (position, rotation, scale) from their parents. For modders, grasping this component is essential for creating complex entity hierarchies, custom behaviors, and ensuring predictable movement and positioning within the game world.

## Overview

The `InheritTransformComponent` dictates how an entity's transform properties are affected by the transform of its parent entity. This is fundamental for creating nested entities, such as a projectile attached to a moving platform or a particle effect that follows a character.

## Component Properties

The `InheritTransformComponent` itself does not have directly configurable properties within the game's XML files. Its behavior is implicitly managed by the entity hierarchy and the game's internal transformation system.

## How Inheritance Works

When an entity has a parent, its transform is calculated relative to its parent's transform. This means:

*   **Position:** An entity's position is its local position offset from its parent's origin.
*   **Rotation:** An entity's rotation is applied after its parent's rotation.
*   **Scale:** An entity's scale is applied after its parent's scale.

This creates a chain of transformations. If Entity C is a child of Entity B, and Entity B is a child of Entity A, then Entity C's final world transform is a result of applying its local transform, then Entity B's local transform, and finally Entity A's local transform.

### Example Scenario

Consider a simple hierarchy:

1.  **Parent Entity (e.g., a moving platform):** Has a world position, rotation, and scale.
2.  **Child Entity (e.g., a crate on the platform):** Has a local position relative to the platform's center, a local rotation, and a local scale.

As the parent entity moves, rotates, or scales, the child entity will automatically update its world position, rotation, and scale to reflect these changes, maintaining its relative offset and orientation.

## Modding Implications

Understanding `InheritTransformComponent` is vital for:

*   **Parenting Entities:** When spawning entities via Lua or XML, correctly setting up parent-child relationships is key for predictable behavior.
*   **Custom Movement:** Implementing complex movement patterns for entities that need to follow other moving objects.
*   **Visual Effects:** Attaching particle effects or other visual elements to entities that should move and rotate with them.
*   **UI Elements:** Positioning UI elements relative to game objects.

### Example: Spawning a Child Entity

While `InheritTransformComponent` isn't directly added as a component in XML, the parenting is established when an entity is spawned.

**XML Example (Conceptual - parenting is often handled by game logic or specific components):**

In many cases, parenting is implicitly handled by how entities are defined or spawned. For instance, a projectile might be spawned with a specific parent entity ID.

**Lua Example:**

You can use the `Entity.SetParent()` function in Lua to establish a parent-child relationship.

```lua
-- Assume 'parent_entity' is a valid Entity object
-- Assume 'child_entity_data' is a table containing the data for the child entity

local parent_entity = Game.GetEntityByName("my_moving_platform") -- Example: Get a parent entity
local child_entity_data = {
    id = "my_child_object",
    components = {
        {
            id = "transform",
            x = 10, -- Local X position relative to parent
            y = 5,  -- Local Y position relative to parent
            rotation = 45, -- Local rotation
            scale_x = 1.5,
            scale_y = 1.5
        },
        -- Other components for the child entity
    }
}

if parent_entity then
    local child_entity = EntityFactory.CreateEntity(child_entity_data)
    if child_entity then
        child_entity.SetParent(parent_entity)
        Game.SpawnEntity(child_entity)
        print("Child entity spawned and parented successfully.")
    else
        print("Failed to create child entity.")
    end
else
    print("Parent entity not found.")
end
```

## Related Components and Concepts

*   **`TransformComponent`**: The fundamental component that holds an entity's local position, rotation, and scale. `InheritTransformComponent` builds upon this.
*   **Entity Hierarchy**: The tree-like structure of parent-child relationships between entities.
*   **World Transform**: The final, calculated transform of an entity in world space, taking into account its own local transform and the transforms of all its ancestors.

## Further Reading

*   [Modding:Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Modding:Components](https://noita.wiki.gg/wiki/Modding:_Components)