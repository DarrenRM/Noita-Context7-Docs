---
title: Vihta Wand Item
category: entities
---

# Vihta Wand Item

This document describes the `wand_vihta.xml` entity, which defines a specific type of wand in Noita.

## Key Components

### Base Entity
The wand inherits its base properties from `data/entities/items/wand_level_03_better.xml`.

### Hotspot Component
Defines the firing position for the wand.
*   `_tags`: "shoot_pos"
*   `offset.x`: 17
*   `offset.y`: 0

### Lua Component (Procedural Wand Logic)
This component handles the procedural generation and behavior of the wand.
*   `execute_on_added`: 1 (Script runs when the wand is added to the game)
*   `execute_every_n_frame`: 181 (Script execution interval)
*   `remove_after_executed`: 0 (Script persists after execution)
*   `script_source_file`: `data/scripts/gun/procedural/wand_vihta.lua`

### Variable Storage Component (Always Cast Action)
Stores a variable related to an "always cast" effect.
*   `name`: "always_cast_action"
*   `value_string`: "HITFX_EXPLOSION_ALCOHOL"

### Lua Component (Add Always Cast)
This component adds an "always cast" functionality to the wand.
*   `script_source_file`: `data/scripts/gun/procedural/wand_add_always_cast.lua`
*   `execute_on_added`: 1 (Script runs when the wand is added)
*   `remove_after_executed`: 1 (Script is removed after execution)