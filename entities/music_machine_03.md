---
title: Music Machine 03
category: entities
---

# Music Machine 03

This document describes the `music_machine_03.xml` entity, a type of music machine in Noita.

## Entity Definition

The core of this entity is defined by its tags and its base entity.

### Key Attributes

*   **`tags`**: `mortal`, `musicmachine`, `musicmachine4`
    *   `mortal`: Indicates the entity can be damaged or destroyed.
    *   `musicmachine`: Identifies it as a music-playing entity.
    *   `musicmachine4`: A specific identifier for this variant of music machine.

### Base Entity

*   **`Base file="data/entities/props/music_machines/base_music_machine.xml"`**: This entity inherits its fundamental properties and behaviors from a common base file for music machines.

## Components

This entity utilizes a Lua component to define its unique behavior.

### LuaComponent

*   **`script_kick="data/entities/props/music_machines/music_machine_03.lua"`**: This attribute points to the Lua script responsible for the specific functionality of `music_machine_03`. This script likely handles the music playback logic, triggers, and any unique interactions associated with this machine.