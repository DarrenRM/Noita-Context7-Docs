---
title: Gravity Field Entity
category: scripts
---

# Gravity Field Entity

This entity defines a gravity field projectile, primarily used for its visual effects and the Lua script that controls its behavior.

## Core Components

### LuaComponent
This component links the entity to its behavior script.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script that defines the entity's logic.                     |
| `execute_every_n_frame` | How often the script's `update` function is called (1 means every frame). |

### ParticleEmitterComponent (x2)
These components are responsible for emitting visual particles that represent the gravity field.

| Attribute                 | Description