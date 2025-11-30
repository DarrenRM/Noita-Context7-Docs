---
title: Wand Vasta Item Configuration
category: entities
---

# Wand Vasta Item Configuration

This document details the configuration for the "Wand Vasta" item in Noita, focusing on its AI-assisted modding relevant attributes.

## Entity Structure

The `Wand Vasta` entity inherits its base properties from `data/entities/items/wand_level_03_better.xml`.

## Key Components

### HotspotComponent

This component defines the firing position for the wand.

| Attribute | Value | Description |
|---|---|---|
| `_tags` | `shoot_pos` | Identifies this hotspot as the primary shooting position. |
| `offset.x` | `18` | Horizontal offset from the entity's origin. |
| `offset.y` | `0` | Vertical offset from the entity's origin. |

### LuaComponent (Procedural Wand Logic)

This component executes a Lua script to define the wand's procedural generation and behavior.

| Attribute | Value | Description |
|---|---|---|
| `execute_on_added` | `1` | The script is executed once when the item is added to the game. |
| `execute_every_n_frame` | `181` | The script is executed periodically every 181 frames. |
| `remove_after_executed` | `0` | The component is not removed after execution. |
| `script_source_file` | `data/scripts/gun/procedural/wand_vasta.lua` | Path to the Lua script responsible for the wand's procedural generation. |

### VariableStorageComponent (Always Cast Action)

This component stores a specific action to be "always cast" by the wand.

| Attribute | Value | Description |
|---|---|---|
| `name` | `always_cast_action` | The name of the variable storing the action. |
| `value_string` | `HITFX_CRITICAL_WATER` | The specific action to be always cast. In this case, it triggers a critical water hit effect. |

### LuaComponent (Add Always Cast)

This component adds the "always cast" functionality to the wand.

| Attribute | Value | Description |
|---|---|---|
| `script_source_file` | `data/scripts/gun/procedural/wand_add_always_cast.lua` | Path to the Lua script that implements the "always cast" feature. |
| `execute_on_added` | `1` | The script is executed once when the item is added. |
| `remove_after_executed` | `1` | The component is removed after its execution, as its function is to set up the always cast behavior. |