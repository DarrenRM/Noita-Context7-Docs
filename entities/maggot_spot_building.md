---
title: Maggot Spot Building
category: entities
---

# Maggot Spot Building

This document describes the `maggotspot.xml` entity, which represents a building in Noita that spawns maggots.

## Core Functionality

The primary function of this entity is to periodically spawn maggots.

### Key Components

*   **`LuaComponent`**: This component links the entity to its associated Lua script (`data/scripts/buildings/maggotspot.lua`), which handles the spawning logic.
    *   `script_source_file`: Specifies the path to the Lua script.
    *   `execute_every_n_frame`: Determines how often the Lua script's logic is executed. In this case, it runs every 20 frames.

## Lua Script (`maggotspot.lua`)

The `maggotspot.lua` script (located at `data/scripts/buildings/maggotspot.lua`) contains the specific logic for how and when maggots are spawned. This would typically involve:

*   Checking conditions for spawning (e.g., proximity to player, biome type).
*   Instantiating maggot entities.
*   Potentially managing the rate or number of maggots spawned.

**Note:** The exact implementation details of the Lua script are not provided in the `maggotspot.xml` file itself, but this component clearly indicates its crucial role.