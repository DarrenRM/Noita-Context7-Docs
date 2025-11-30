---
title: Wand Kiekurakeppi
category: entities
---

# Wand Kiekurakeppi

This document describes the `wand_kiekurakeppi.xml` entity, a type of wand in Noita.

## Core Functionality

The Kiekurakeppi wand is characterized by its unique procedural generation script and an "always cast" effect.

### Base Entity

*   Inherits properties from `data/entities/items/wand_unshuffle_02.xml`.

### Hotspot Component

*   Defines the shooting position for the wand.
    *   `_tags`: "shoot_pos"
    *   `offset.x`: 14
    *   `offset.y`: 0

### Lua Components

This wand utilizes two Lua scripts for its behavior:

1.  **Procedural Wand Generation:**
    *   `script_source_file`: `data/scripts/gun/procedural/wand_kiekurakeppi.lua`
    *   `execute_on_added`: `1` (Executes when the wand is added to the game)
    *   `execute_every_n_frame`: `181` (Indicates a procedural generation interval)
    *   `remove_after_executed`: `0` (The script remains active)

2.  **Always Cast Effect:**
    *   `script_source_file`: `data/scripts/gun/procedural/wand_add_always_cast.lua`
    *   `execute_on_added`: `1` (Executes when the wand is added)
    *   `remove_after_executed`: `1` (The script is removed after execution, applying its effect once)

### Variable Storage Component

*   This component defines a variable used by the `wand_add_always_cast.lua` script.
    *   `name`: "always_cast_action"
    *   `value_string`: "KNOCKBACK" (This specifies that the "always cast" effect is knockback)