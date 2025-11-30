---
title: Food Clock Perk Entity
category: entities
---

# Food Clock Perk Entity

This entity defines the behavior for the "Food Clock" perk in Noita. When acquired, it triggers a Lua script that manages the perk's functionality.

## Key Components

### LuaComponent
This component is responsible for executing the perk's logic.

*   **`script_source_file`**: `data/scripts/projectiles/food_clock.lua`
    *   This specifies the Lua script that handles the perk's effects.
*   **`execute_on_added`**: `1`
    *   The script will be executed immediately when the perk is added to the player.
*   **`remove_after_executed`**: `1`
    *   This component (and thus the perk's immediate effect) is removed after the script has finished executing.

## Associated Scripts

*   `data/scripts/projectiles/food_clock.lua`: This script contains the core logic for the Food Clock perk. Its exact functionality would need to be examined within the script file itself, but it likely involves managing hunger or time-related mechanics.