---
title: Wider Laser Emitter
category: entities
---

# Wider Laser Emitter

This entity defines a wider laser emitter, primarily controlled by a Lua script.

## LuaComponent

This component is responsible for the entity's behavior.

### Key Attributes:

*   **script\_source\_file**: `data/scripts/projectiles/laser_emitter_wider.lua` - Specifies the Lua script that governs the emitter's functionality.
*   **execute\_every\_n\_frame**: `1` - The script will execute every frame.
*   **remove\_after\_executed**: `1` - The entity will be removed after the script has executed once.