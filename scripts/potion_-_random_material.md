---
title: Potion - Random Material
category: guides
---

<Entity tags="hittable,teleportable_NOT,item_physics" >

   <Base file="data/entities/items/pickup/potion.xml" >
    <LuaComponent 
		execute_on_added="1"
		remove_after_executed="1"
		call_init_function="1"
		script_source_file="data/scripts/items/potion_random_material.lua" 
    ></LuaComponent>

   </Base>

</Entity>
```

---
title: Potion - Random Material
category: entities/items/pickup
---

# Potion - Random Material

This entity represents a potion pickup that, when consumed, grants the player a random material.

## Key Attributes

*   **`tags`**: `hittable`, `teleportable_NOT`, `item_physics` - Defines how the entity interacts with the game world. It can be hit, cannot be teleported, and has physics.
*   **`Base file="data/entities/items/pickup/potion.xml"`**: Inherits core properties from the generic `potion.xml` entity. This means it shares fundamental behaviors with other potions.

## Lua Component

This component is crucial for defining the unique behavior of this potion.

*   **`execute_on_added="1"`**: The Lua script will execute immediately when the potion is added to the game world (e.g., when it spawns).
*   **`remove_after_executed="1"`**: The potion entity will be removed from the game after the Lua script has finished executing.
*   **`call_init_function="1"`**: The `init` function within the specified Lua script will be called.
*   **`script_source_file="data/scripts/items/potion_random_material.lua"`**: This points to the external Lua script that contains the logic for determining and applying the random material to the player.

## Associated Script

The behavior of this potion is entirely defined by the `data/scripts/items/potion_random_material.lua` file. This script is responsible for:

1.  Identifying all available materials in the game.
2.  Randomly selecting one of these materials.
3.  Applying the selected material to the player's inventory or current effects.