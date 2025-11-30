---
title: Orb Line Spawner
category: entities
---

# Orb Line Spawner

This entity is responsible for spawning the visual "orb line" effect, often seen in conjunction with certain magical effects or environmental hazards.

## Key Components

### LuaComponent
This component dictates the behavior of the orb line spawner through a Lua script.

*   **`script_source_file`**: `data/scripts/magic/orb_line.lua` - Specifies the Lua script that controls the spawner's logic.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame, ensuring continuous operation.

### LifetimeComponent
This component defines how long the orb line spawner entity will persist.

*   **`lifetime`**: `5` - The entity will exist for 5 seconds before despawning.