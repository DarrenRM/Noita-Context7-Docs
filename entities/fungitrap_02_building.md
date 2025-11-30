---
title: Fungitrap 02 Building
category: entities
---

# Fungitrap 02 Building

This document describes the `fungitrap_02.xml` entity, which represents a fungitrap building in Noita.

## Core Components

### LuaComponent
This component links the building to its associated Lua script for dynamic behavior.

*   **script\_source\_file**: `data/scripts/buildings/fungitrap_02.lua` - Specifies the Lua script that controls the fungitrap's logic.
*   **execute\_every\_n\_frame**: `50` - The script will execute its logic every 50 frames.

### CameraBoundComponent
This component manages the entity's visibility and interaction based on camera proximity.

*   **max\_count**: `30` - The maximum number of these entities that can be active within the camera's view.
*   **distance**: `160000` - The squared distance from the camera within which the entity is considered active.