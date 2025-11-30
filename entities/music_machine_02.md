---
title: Music Machine 02
category: entities
---

# Music Machine 02

This entity represents a specific type of music machine in Noita, identified by its unique identifier `music_machine_02`. It inherits its core functionality from a base music machine entity.

## Key Components

### Base Entity

*   **`file`**: `data/entities/props/music_machines/base_music_machine.xml`
    *   This attribute indicates that `music_machine_02` uses the `base_music_machine.xml` as its foundational structure. This implies shared properties and behaviors with other music machines.

### Lua Component

*   **`script_kick`**: `data/entities/props/music_machines/music_machine_02.lua`
    *   This is the primary script responsible for the unique behavior and functionality of `music_machine_02`. It likely handles the specific music playback, interactions, or visual effects associated with this machine.

## Tags

The entity is tagged with:

*   `mortal`: Suggests it can be destroyed or affected by damage.
*   `musicmachine`: Identifies it as a music-playing entity.
*   `musicmachine3`: A specific identifier for this variant of music machine.