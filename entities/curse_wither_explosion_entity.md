---
title: Curse Wither Explosion Entity
category: entities
---

# Curse Wither Explosion Entity

This entity defines the behavior and visual representation of the "Curse Wither Explosion" effect in Noita. It's primarily used to trigger specific Lua scripts for the curse's start and end phases, manage its lifetime, and display its UI icon.

## Key Components

### VariableStorageComponent

This component stores a string value that identifies the type of curse effect.

*   `_tags`: `effect_curse_wither_type` - Tags the entity as a specific curse type.
*   `value_string`: `explosion` - Specifies that this is an "explosion" type curse.

### LuaComponent (Start)

This component executes a Lua script when the entity is initialized, handling the initial effects of the curse.

*   `script_source_file`: `data/scripts/projectiles/curse_wither_start.lua` - The script responsible for the curse's initial activation.
*   `execute_every_n_frame`: `1` - Executes the script on the first frame.
*   `remove_after_executed`: `1` - The entity is removed after this script has executed.

### LuaComponent (End)

This component executes a Lua script when the entity is removed, handling any cleanup or final effects of the curse.

*   `script_source_file`: `data/scripts/projectiles/curse_wither_end.lua` - The script responsible for the curse's deactivation or final effects.
*   `execute_every_n_frame`: `-1` - This script is not executed on a frame basis.
*   `execute_on_removed`: `1` - The script executes when the entity is removed.

### LifetimeComponent

Manages how long the curse effect persists.

*   `_tags`: `effect_curse_lifetime` - Tags the entity for lifetime management.
*   `lifetime`: `300` - The duration of the curse effect in frames (approximately 5 seconds).

### UIIconComponent

Defines how the curse is represented in the game's user interface.

*   `icon_sprite_file`: `data/ui_gfx/status_indicators/curse_wither_explosion.png` - The sprite file for the curse's icon.
*   `name`: `$status_curse_wither_explosion` - The localized name of the status effect.
*   `description`: `$statusdesc_curse_wither_explosion` - The localized description of the status effect.
*   `display_above_head`: `1` - The icon is displayed above the player's head.
*   `display_in_hud`: `0` - The icon is not displayed in the main HUD.
*   `is_perk`: `1` - Indicates this is treated as a perk-like status.