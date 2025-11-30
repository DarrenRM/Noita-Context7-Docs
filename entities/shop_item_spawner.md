---
title: Shop Item Spawner
category: entities
---

# Shop Item Spawner

This entity is responsible for spawning random shop items. It's a temporary entity that executes a Lua script upon being added and then removes itself.

## Key Components

### LuaComponent
This component executes a Lua script to handle the spawning logic.

*   **`script_source_file`**: `data/scripts/items/spawn_random_shop_item.lua` - The script that handles the spawning of random shop items.
*   **`execute_on_added`**: `1` - Ensures the script runs immediately when the entity is added.
*   **`remove_after_executed`**: `1` - The entity is removed after the script has finished executing, preventing it from lingering.

### LifetimeComponent
This component defines how long the entity exists.

*   **`lifetime`**: `5` - The entity will exist for 5 frames before being removed.