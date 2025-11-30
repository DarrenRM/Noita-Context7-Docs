---
title: Winter Ruins Spawner Entity
category: entities
---

---

# Winter Ruins Spawner Entity

This entity is responsible for spawning enemies and other elements within the Winter Ruins biome. It utilizes a Lua script to manage its spawning logic.

## Key Components

### LuaComponent

This component defines the behavior of the spawner through a Lua script.

*   **`script_source_file`**: `data/scripts/props/overworld_winter_ruins_spawner.lua`
    *   Specifies the path to the Lua script that controls the spawner's functionality.
*   **`execute_on_added`**: `1`
    *   Indicates that the script should be executed immediately when the entity is added to the game world.
*   **`execute_every_n_frame`**: `-1`
    *   This value suggests that the script is not intended to run on a recurring frame-by-frame basis, but rather is likely triggered by specific events or conditions defined within the Lua script itself.

## Associated Script

The primary logic for this spawner is contained within:

```lua
-- data/scripts/props/overworld_winter_ruins_spawner.lua
-- (Content of the Lua script would be detailed here if available)
```

This script would typically handle:
*   Defining spawn points.
*   Selecting enemy types based on biome progression or other factors.
*   Controlling spawn rates and wave patterns.
*   Potentially spawning environmental props or effects.