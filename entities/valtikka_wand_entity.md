---
title: Valtikka Wand Entity
category: entities
---

# Valtikka Wand Entity

This document describes the `wand_valtikka.xml` entity, which defines a specific type of wand in Noita.

## Core Components

### Base Entity
The wand inherits its base properties from `data/entities/items/wand_level_03.xml`.

### Hotspot Component
Defines the primary shooting position for the wand.
*   `_tags`: "shoot_pos" - Identifies this as a shooting origin.
*   `offset.x`: 16 - Horizontal offset from the wand's center.
*   `offset.y`: 0 - Vertical offset from the wand's center.

### Lua Component (Procedural Wand Logic)
This component executes Lua scripts to define the wand's unique behavior.
*   `execute_on_added`: 1 - The script runs when the wand is first added to the game.
*   `execute_every_n_frame`: 181 - The script logic is re-evaluated every 181 frames.
*   `remove_after_executed`: 0 - The script remains active.
*   `script_source_file`: `data/scripts/gun/procedural/wand_valtikka.lua` - The primary script file for this wand's procedural generation.

### Variable Storage Component (Always Cast Action)
Stores a specific action that the wand will always attempt to cast.
*   `name`: "always_cast_action" - The name of the variable.
*   `value_string`: "PIERCING_SHOT" - The action to be always cast.

### Lua Component (Add Always Cast)
This component adds the "always cast" functionality to the wand.
*   `script_source_file`: `data/scripts/gun/procedural/wand_add_always_cast.lua` - The script responsible for implementing the always cast behavior.
*   `execute_on_added`: 1 - The script runs when the wand is added.
*   `remove_after_executed`: 1 - The script is removed after execution, as its function is to modify the wand's properties.