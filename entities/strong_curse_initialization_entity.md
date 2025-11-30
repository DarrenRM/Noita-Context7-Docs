---
title: Strong Curse Initialization Entity
category: entities
---

# Strong Curse Initialization Entity

This entity is a simple container for a Lua script that handles the initialization of a strong curse effect. It doesn't have any visual or physical properties itself, but rather triggers a script to manage the curse's behavior.

## Key Components

### LuaComponent

This is the primary component responsible for executing the curse's logic.

*   **`script_source_file`**: Specifies the path to the Lua script that contains the curse's initialization and behavior.
    *   Value: `data/scripts/projectiles/curse_strong_init.lua`
*   **`execute_every_n_frame`**: Determines how frequently the script's logic is executed.
    *   Value: `1` (meaning it executes every frame)

## Purpose

The `curse_strong_init.xml` entity serves as a trigger for the `curse_strong_init.lua` script. When this entity is spawned in the game, the associated Lua script will run, likely to apply a strong curse effect to the player or a specific area. The script itself would contain the detailed logic for how the curse manifests, its duration, and its effects.