---
title: Curse Stronger Initialization Script
category: entities
---

# Curse Stronger Initialization Script

This entity is responsible for initializing the "stronger curse" effect in Noita. It achieves this by executing a Lua script at a regular interval.

## Key Components

### LuaComponent

This component is the core of the entity's functionality.

*   **`script_source_file`**: `data/scripts/projectiles/curse_stronger_init.lua`
    *   This specifies the Lua script that will be executed. This script likely contains the logic for how the "stronger curse" is applied or managed within the game.
*   **`execute_every_n_frame`**: `1`
    *   This attribute indicates that the Lua script will be executed every single frame. This suggests a continuous or very frequent update mechanism for the curse effect.

## Purpose

The primary purpose of this entity is to trigger and manage the "stronger curse" game mechanic. By linking a Lua script that runs every frame, it allows for dynamic and potentially complex behavior associated with this curse.

## AI Modding Considerations

When modding this entity, the focus would be on understanding and potentially modifying the `curse_stronger_init.lua` script. This script will dictate:

*   How the "stronger curse" is detected or triggered.
*   What specific gameplay changes constitute the "stronger curse" (e.g., increased enemy difficulty, altered spell behavior, environmental hazards).
*   The duration or conditions for the curse's activation and deactivation.

Modders could alter the script to:

*   Introduce new curse effects.
*   Modify the intensity or frequency of existing curse effects.
*   Change the conditions under which the curse is applied.
*   Integrate the curse with other modded mechanics.