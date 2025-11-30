---
title: Hearty Status Effect
category: entities
---

# Hearty Status Effect

This entity defines the "Hearty" status effect in Noita. It's a temporary buff that affects the player's health regeneration.

## Key Components

### LuaComponent (Start Effect)
This component triggers the initial logic for the Hearty effect.

*   **`script_source_file`**: `data/scripts/status_effects/hearty_start.lua` - Contains the Lua code to apply the effect when it begins.
*   **`execute_every_n_frame`**: `4` - The script runs every 4 frames.
*   **`remove_after_executed`**: `1` - The component is removed after its initial execution.

### LuaComponent (End Effect)
This component handles the cleanup logic when the Hearty effect is removed.

*   **`script_source_file`**: `data/scripts/status_effects/hearty_end.lua` - Contains the Lua code to revert the effect when it ends.
*   **`execute_on_removed`**: `1` - The script executes when the status effect is removed.

### VariableStorageComponent
Stores a variable associated with this effect.

*   **`name`**: `effect_hearty` - The identifier for the stored variable.
*   **`value_float`**: `0.0` - The initial float value.

### LifetimeComponent
Determines how long the status effect lasts.

*   **`lifetime`**: `1200` - The effect lasts for 1200 frames (20 seconds).

### UIIconComponent
Defines how the status effect is displayed in the user interface.

*   **`name`**: `$status_hearty` - The internal name for the UI element.
*   **`description`**: `$statusdesc_hearty` - The localized description text for the effect.
*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/hearty.png` - The sprite used to represent the effect in the UI.
*   **`display_in_hud`**: `1` - The effect is shown in the Heads-Up Display.