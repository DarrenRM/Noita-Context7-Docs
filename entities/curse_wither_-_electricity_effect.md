---
title: Curse Wither - Electricity Effect
category: entities
---

# Curse Wither - Electricity Effect

This entity defines the visual and functional aspects of the "Curse Wither - Electricity" status effect in Noita. It's primarily used to apply a temporary debuff that visually represents electrical energy.

## Key Components

### VariableStorageComponent

This component stores a string value that identifies the type of curse.

*   **`_tags`**: `effect_curse_wither_type` - Tags the entity as a specific type of curse.
*   **`value_string`**: `electricity` - Specifies that this is the electricity variant of the curse.

### LuaComponent (Start Effect)

This component triggers a Lua script when the entity is first activated, likely to initiate the visual and gameplay effects of the curse.

*   **`script_source_file`**: `data/scripts/projectiles/curse_wither_start.lua` - The script responsible for starting the curse's effects.
*   **`execute_every_n_frame`**: `1` - The script executes every frame.
*   **`remove_after_executed`**: `1` - The component is removed after the script has executed once.

### LuaComponent (End Effect)

This component triggers a Lua script when the entity is removed, likely to clean up any lingering effects or animations.

*   **`script_source_file`**: `data/scripts/projectiles/curse_wither_end.lua` - The script responsible for ending the curse's effects.
*   **`execute_every_n_frame`**: `-1` - The script does not execute on a frame interval.
*   **`execute_on_removed`**: `1` - The script executes when the entity is removed.

### LifetimeComponent

This component manages how long the curse effect persists.

*   **`_tags`**: `effect_curse_lifetime` - Tags the component for lifetime management.
*   **`lifetime`**: `300` - The curse effect will last for 300 frames.

### UIIconComponent

This component defines how the curse is displayed in the game's user interface.

*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/curse_wither_electricity.png` - The sprite used for the status icon.
*   **`name`**: `$status_curse_wither_electricity` - The localized name of the status effect.
*   **`description`**: `$statusdesc_curse_wither_electricity` - The localized description of the status effect.
*   **`display_above_head`**: `1` - The icon is displayed above the character's head.
*   **`display_in_hud`**: `0` - The icon is not displayed in the main HUD.
*   **`is_perk`**: `1` - Indicates this is treated as a perk-like status.