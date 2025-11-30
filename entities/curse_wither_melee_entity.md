---
title: Curse Wither Melee Entity
category: entities
---

# Curse Wither Melee Entity

This entity defines the "Wither Melee" curse effect in Noita. It's a status effect that applies a debuff to the player, primarily affecting melee attacks.

## Key Components

### VariableStorageComponent

This component stores the type of curse.

*   **_tags**: `effect_curse_wither_type` - Identifies this as a wither curse.
*   **value_string**: `melee` - Specifies that this curse affects melee.

### LuaComponent (Start Effect)

This component triggers the initial logic for the curse.

*   **script_source_file**: `data/scripts/projectiles/curse_wither_start.lua` - The script executed when the curse is applied.
*   **execute_every_n_frame**: `1` - Executes the script on the first frame.
*   **remove_after_executed**: `1` - Removes this component after execution.

### LuaComponent (End Effect)

This component handles the logic when the curse ends or is removed.

*   **script_source_file**: `data/scripts/projectiles/curse_wither_end.lua` - The script executed when the curse expires or is removed.
*   **execute_every_n_frame**: `-1` - This indicates it's not meant for continuous frame execution.
*   **execute_on_removed**: `1` - Triggers the script when the entity is removed.

### LifetimeComponent

This component manages how long the curse effect lasts.

*   **_tags**: `effect_curse_lifetime` - Identifies this as a lifetime component for curses.
*   **lifetime**: `300` - The duration of the curse in frames (approximately 5 seconds).

### UIIconComponent

This component defines how the curse is displayed to the player.

*   **icon_sprite_file**: `data/ui_gfx/status_indicators/curse_wither_melee.png` - The sprite used for the status icon.
*   **name**: `$status_curse_wither_melee` - The localized name of the status effect.
*   **description**: `$statusdesc_curse_wither_melee` - The localized description of the status effect.
*   **display_above_head**: `1` - The icon is displayed above the player's head.
*   **display_in_hud**: `0` - The icon is not displayed in the main HUD.
*   **is_perk**: `1` - This indicates it's treated similarly to a perk in terms of UI display.