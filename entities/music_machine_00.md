---
title: Music Machine 00
category: entities
---

---

# Music Machine 00

This document describes the `music_machine_00.xml` entity, a basic music machine prop in Noita.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

### Key Attributes

*   **tags**: `mortal`, `musicmachine`, `musicmachine1` - These tags categorize the entity, indicating it can be damaged, is a music machine, and specifically is the first variant.

## Base Entity

This music machine inherits its fundamental properties from a base entity.

### Key Elements

*   **Base file**: `data/entities/props/music_machines/base_music_machine.xml` - This specifies the parent XML file from which this entity derives its common behaviors and properties.

## Lua Component

This entity utilizes a Lua script to define its unique functionality.

### Key Elements

*   **script_kick**: `data/entities/props/music_machines/music_machine_00.lua` - This attribute points to the Lua script responsible for the specific behaviors of this music machine, such as playing music or interacting with the player.