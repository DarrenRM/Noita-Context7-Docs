---
title: Pollen Ball Burst Entity
category: entities
---

# Pollen Ball Burst Entity

This entity defines the behavior and lifespan of a pollen ball burst effect in Noita.

## Core Components

### LuaComponent
This component links the entity to a Lua script that handles its dynamic behavior.

*   **`script_source_file`**: `data/scripts/projectiles/pollen_ball_burst.lua` - Specifies the Lua script responsible for the burst's logic.
*   **`execute_every_n_frame`**: `1` - Indicates that the script's logic should be executed every frame.

### LifetimeComponent
This component controls how long the entity persists in the game world.

*   **`lifetime`**: `5` - The entity will exist for 5 seconds before being removed.