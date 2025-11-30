---
title: Fly Upwards Projectile Component
category: entities
---

# Fly Upwards Projectile Component

This entity component is designed to make a projectile move upwards. It utilizes a Lua script to achieve this behavior.

## LuaComponent

This is the primary component responsible for the entity's behavior.

### Key Attributes:

*   **`script_source_file`**: Specifies the Lua script file that controls the entity's logic.
    *   Value: `data/scripts/projectiles/fly_upwards.lua`
*   **`execute_every_n_frame`**: Determines how often the script's logic is executed.
    *   Value: `20` (The script will run every 20 frames).
*   **`remove_after_executed`**: Indicates whether the entity should be removed after the script has executed.
    *   Value: `1` (The entity will be removed after the script runs).