---
title: Base Wand Pickup Entity
category: entities
---

# Base Wand Pickup Entity

This entity defines the fundamental behavior and properties of a wand when it is picked up by the player in Noita. It primarily uses Lua components to handle the pickup logic and any associated effects.

## Key Components and Attributes

### LuaComponent (Pickup Logic)

This component is responsible for executing a script when the wand is picked up.

*   **`script_item_picked_up`**: Specifies the Lua script to execute upon pickup. In this case, it's `data/scripts/particles/wand_pickup.lua`, which likely handles visual effects or immediate wand adjustments.
*   **`remove_after_executed`**: Set to "0", meaning the component (and potentially the entity) is not removed immediately after the script runs.

```xml
<LuaComponent 
    _enabled="1" 
    execute_every_n_frame="-1"
    script_item_picked_up="data/scripts/particles/wand_pickup.lua"
    remove_after_executed="0"		
>
</LuaComponent>
```

### MaterialAreaCheckerComponent (Charmed Wands)

This component is used to detect specific materials within a defined area, primarily for handling "charmed" wands.

*   **`update_every_x_frame`**: Sets how often the component checks for materials (every 20 frames).
*   **`area_aabb.min_x`, `area_aabb.min_y`, `area_aabb.max_x`, `area_aabb.max_y`**: Defines a bounding box around the entity to check for materials. This specific configuration creates a small area directly above and in front of the wand.
*   **`material`**, **`material2`**: Specifies the materials to look for. Here, it's `magic_liquid_charm`, indicating that if the wand is touched by this liquid, a specific action will occur.

```xml
<MaterialAreaCheckerComponent 
    _tags="enabled_in_world"
    update_every_x_frame="20"
    look_for_failure="0"
    area_aabb.min_x="-2" 
    area_aabb.min_y="-4"        
    area_aabb.max_x="2" 
    area_aabb.max_y="0"     
    material="magic_liquid_charm"
    material2="magic_liquid_charm"
    kill_after_message="0"
    />
```

### LuaComponent (Charmed Wand Script)

This component is triggered when the `MaterialAreaCheckerComponent` successfully detects the specified materials.

*   **`script_material_area_checker_success`**: Points to the Lua script that executes when the `magic_liquid_charm` is detected within the checker's area. In this case, it's `data/scripts/animals/wand_charm.lua`, suggesting a script that applies a "charm" effect to the wand.

```xml
<LuaComponent
    _tags="enabled_in_world"
    script_material_area_checker_success="data/scripts/animals/wand_charm.lua" >
</LuaComponent>
```