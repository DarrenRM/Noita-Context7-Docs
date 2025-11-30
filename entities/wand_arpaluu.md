---
title: Wand Arpaluu
category: entities
---

# Wand Arpaluu

This document describes the `wand_arpaluu.xml` entity, a type of wand in Noita.

## Base Entity

The wand inherits its base properties from `data/entities/items/wand_unshuffle_05.xml`.

### Key Components

*   **HotspotComponent**: Defines the shooting position for the wand.
    *   `offset.x`: 21
    *   `offset.y`: 0

*   **LuaComponent (execute_on_added)**: This component executes a Lua script when the wand is added to the game.
    *   `execute_every_n_frame`: 181 (Indicates a periodic action or effect).
    *   `remove_after_executed`: 0 (The component persists after execution).
    *   `script_source_file`: `data/scripts/gun/procedural/wand_arpaluu.lua` (The primary script for this wand's unique behavior).

*   **VariableStorageComponent**: Stores a specific variable.
    *   `name`: `always_cast_action`
    *   `value_string`: `EXPLOSION_REMOVE` (Suggests an effect related to explosions and removal).

*   **LuaComponent (wand_add_always_cast)**: This component adds an "always cast" functionality to the wand.
    *   `script_source_file`: `data/scripts/gun/procedural/wand_add_always_cast.lua`
    *   `execute_on_added`: 1 (Executes when the wand is added).
    *   `remove_after_executed`: 1 (This component is removed after its initial execution, meaning the "always cast" effect is applied once).

## Summary

The `wand_arpaluu.xml` entity defines a wand that utilizes a procedural script (`wand_arpaluu.lua`) for its unique behavior. It also incorporates an "always cast" effect related to explosions and removal, managed by a separate Lua script. The `HotspotComponent` defines its firing origin.