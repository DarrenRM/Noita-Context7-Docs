---
title: Line Arc Projectile
category: entities
---

# Line Arc Projectile

This entity defines a projectile that creates a line-shaped arc effect.

## LuaComponent

This component is responsible for the projectile's behavior.

### Key Attributes:

*   **`script_source_file`**: Specifies the Lua script that governs the projectile's logic. In this case, it's `data/scripts/projectiles/line_arc.lua`.
*   **`execute_every_n_frame`**: Determines how often the script's logic is executed. A value of `1` means it executes every frame.