---
title: Give All Perks Item
category: entities
---

# Give All Perks Item

This entity represents an item that, when picked up, grants the player all available perks.

## Key Components

### LuaComponent
This component is responsible for the core functionality of the item.

*   **`script_source_file`**: `data/scripts/perks/give_all_perks.lua` - Specifies the Lua script that handles the perk granting logic.
*   **`execute_on_added`**: `1` - The script will execute immediately when the item is added to the game world.
*   **`execute_every_n_frame`**: `-1` - The script will only execute once.
*   **`execute_times`**: `1` - Confirms the script executes only one time.

### LifetimeComponent
This component defines how long the item will persist in the game world.

*   **`lifetime`**: `5` - The item will disappear after 5 seconds.