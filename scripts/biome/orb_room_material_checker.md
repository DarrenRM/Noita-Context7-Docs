---
title: Orb Room Material Checker
category: scripts/biome
---

# Orb Room Material Checker

This script provides functionality for creating and managing "material checker" entities within Noita's orb rooms. These entities are designed to detect specific materials and trigger subsequent actions, such as spawning visual effects.

## Core Functionality

The primary purpose of this script is to facilitate the creation of entities that act as triggers based on the presence of a particular material.

### `spawn_material_checker` Function

This function is responsible for instantiating a material checker entity.

**Key Parameters:**

*   `x`, `y`: The world coordinates where the checker entity will be placed.
*   `material1_str`: A string representing the name of the material to be detected (e.g., `"GOLD"`).
*   `lua_filename`: The name of the Lua script to be executed when the material is successfully detected.
*   `image_emitter`: The entity ID of the visual effect (emitter) to spawn upon successful detection.
*   `image_emitter_x`, `image_emitter_y`: The coordinates where the `image_emitter` will be spawned.

**Internal Logic:**

1.  Loads the `orb_room_materialchecker.xml` entity template.
2.  Retrieves the numerical ID for the specified `material1_str`.
3.  Configures the `MaterialAreaCheckerComponent` to look for `material1`.
4.  Sets the `LuaComponent`'s `script_material_area_checker_success` to the provided `lua_filename`. This links the material detection to a specific script.
5.  Adds `VariableStorageComponent`s to store the `emitter_x`, `emitter_y`, and `emitter` information, which will be used by the success script.

### `material_area_checker_success` Function

This function is designed to be called when the `MaterialAreaCheckerComponent` successfully detects the target material.

**Key Actions:**

1.  Retrieves the `entity_id` of the entity that triggered this function.
2.  Retrieves the stored `image_emitter`, `image_x`, and `image_emitter_y` values from the `VariableStorageComponent`s of the triggering entity.
3.  Loads the specified `image_emitter` entity at the stored coordinates.

## Example Usage (Conceptual)

```lua
-- Example of how spawn_material_checker might be used in another script
-- Assuming 'orb_room_materialchecker.xml' and 'data/scripts/orbroom_success_effect.lua' exist

local x_pos = 100
local y_pos = 200
local material_to_detect = "GOLD"
local success_script = "data/scripts/orbroom_success_effect.lua"
local effect_to_spawn = "data/entities/particles/spark.xml"
local effect_x = x_pos + 10
local effect_y = y_pos

spawn_material_checker( x_pos, y_pos, material_to_detect, success_script, effect_to_spawn, effect_x, effect_y )
```

This would create a material checker at `(100, 200)` that, upon detecting "GOLD", would execute `orbroom_success_effect.lua` and spawn a "spark" particle effect at `(110, 200)`.