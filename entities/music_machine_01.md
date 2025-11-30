---
title: Music Machine 01
category: entities
---

# Music Machine 01

This document describes the `music_machine_01.xml` entity, a basic music machine prop in Noita.

## Entity Definition

The `music_machine_01` entity is a prop designed to play music. It inherits its base functionality from `base_music_machine.xml`.

### Key Attributes

*   **tags**: `mortal`, `musicmachine`, `musicmachine2` - These tags define the entity's properties and how it interacts with the game world.

### Components

*   **Base**: `data/entities/props/music_machines/base_music_machine.xml` - This specifies the foundational properties and behaviors of the music machine.
*   **LuaComponent**:
    *   `script_kick`: `data/entities/props/music_machines/music_machine_01.lua` - This component links the entity to a Lua script that likely handles its specific music-playing logic and interactions.