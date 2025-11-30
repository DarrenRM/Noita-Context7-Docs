---
title: Curse Wither Projectile Entity
category: entities
---

# Curse Wither Projectile Entity

This entity defines the behavior and appearance of the "Curse Wither" projectile effect in Noita. It's primarily controlled by Lua scripts and has a defined lifetime and UI representation.

## Key Components

### VariableStorageComponent

This component stores a string value that likely categorizes this entity.

*   `_tags`: `effect_curse_wither_type` - Identifies this as a curse wither effect.
*   `value_string`: `projectile` - Specifies that this is a projectile type of effect.

### LuaComponent (Start)

This component executes a Lua script once when the entity is created to initiate the curse wither effect.

*   `script_source_file`: `data/scripts/projectiles/curse_wither_start.lua` - The script responsible for the initial application of the curse.
*   `execute_every_n_frame`: `1` - Executes on the first frame.
*   `remove_after_executed`: `1` - The component is removed after its execution.

### LuaComponent (End)

This component executes a Lua script when the entity is removed, likely for cleanup or final effect application.

*   `script_source_file`: `data/scripts/projectiles/curse_wither_end.lua` - The script responsible for the termination of the curse effect.
*   `execute_every_n_frame`: `-1` - This script does not execute on a frame basis.
*   `execute_on_removed`: `1` - The script runs when the entity is removed.

### LifetimeComponent

This component manages how long the curse wither projectile effect persists.

*   `_tags`: `effect_curse_lifetime` - Tags related to the lifetime of curse effects.
*   `lifetime`: `300` - The duration of the effect in frames (approximately 5 seconds).

### UIIconComponent

This component defines how the curse wither effect is displayed in the game's UI.

*   `icon_sprite_file`: `data/ui_gfx/status_indicators/curse_wither_projectile.png` - The sprite used for the status icon.
*   `name`: `$status_curse_wither_projectile` - The localized name of the status effect.
*   `description`: `$statusdesc_curse_wither_projectile` - The localized description of the status effect.
*   `display_above_head`: `1` - The icon is displayed above the affected character's head.
*   `display_in_hud`: `0` - The icon is not displayed in the main HUD.
*   `is_perk`: `1` - Indicates this might be treated similarly to a perk in some UI contexts.