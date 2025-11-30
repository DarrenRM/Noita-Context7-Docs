---
title: Potion Effect Particle Emitter
category: scripts/
---

# Potion Effect Particle Emitter

This script defines the behavior for the particle effect that appears when a potion is picked up. It's responsible for spawning a visual effect that matches the potion's color.

## Key Functionality

### `item_pickup(entity_item, entity_who_picked, name)`

This function is called when an item (specifically a potion in this context) is picked up.

*   **`entity_item`**: The entity representing the potion item being picked up.
*   **`entity_who_picked`**: The entity that picked up the item (usually the player).
*   **`name`**: The internal name of the item.

The function performs the following actions:

1.  **Get Potion Color**: Retrieves the color of the potion using `GameGetPotionColorUint`. This color will be used for the particle effect.
2.  **Check if Player Picked Up**: It checks if the item has already been picked up by the player. This prevents duplicate effects if the item is somehow interacted with multiple times.
3.  **Spawn Particle Effect**: If the item is being picked up for the first time by the player, it loads and spawns a particle emitter entity (`data/entities/particles/image_emitters/potion_effect.xml`) at the potion's location.
4.  **Apply Color to Emitter**: The `edit_component` function is used to modify the `ParticleEmitterComponent` of the spawned particle entity, setting its `color` variable to match the potion's color.

## Core Components Involved

*   **`ItemComponent`**: Used to check if the item has been picked up by the player.
*   **`ParticleEmitterComponent`**: The component on the spawned particle entity that controls the visual particle effect.

## Example Usage (Conceptual)

This script is typically attached to potion items. When a player collides with a potion entity that has this script, the `item_pickup` function will be triggered, resulting in a colored particle burst.

```lua
-- Example of how a potion entity might be defined (simplified)
-- This is NOT part of the provided script, but illustrates its context.

-- potion_of_healing.xml
-- ...
-- <components>
--     <ItemComponent
--         name="potion_of_healing"
--         is_potion="true"
--         ...
--     />
--     <LuaComponent
--         script_path="data/scripts/items/potion_effect.lua"
--     />
--     ...
-- </components>
-- ...
```