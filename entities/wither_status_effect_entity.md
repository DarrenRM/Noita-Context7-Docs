---
title: Wither Status Effect Entity
category: entities
---

# Wither Status Effect Entity

This entity defines the "Wither" status effect in Noita. It primarily uses Lua scripts to manage its behavior and has a visual representation in the UI.

## Key Components

### LuaComponent (Start)

*   **`script_source_file`**: `data/scripts/status_effects/wither_start.lua`
    *   This script is executed once when the status effect is applied to initiate the wither effect.
*   **`execute_every_n_frame`**: `4`
    *   The script will run every 4 frames.
*   **`remove_after_executed`**: `1`
    *   This component will be removed after its script has executed.

### LuaComponent (End)

*   **`script_source_file`**: `data/scripts/status_effects/wither_end.lua`
    *   This script is executed when the status effect is removed, handling any cleanup or finalization.
*   **`execute_every_n_frame`**: `-1`
    *   Indicates this component doesn't execute on a frame interval.
*   **`execute_on_removed`**: `1`
    *   The script will execute when the entity or status effect is removed.

### LifetimeComponent

*   **`lifetime`**: `1800`
    *   The status effect will persist for 1800 frames (approximately 30 seconds).

### UIIconComponent

*   **`name`**: `$status_wither`
    *   The internal name for the status effect, likely used for localization.
*   **`description`**: `$statusdesc_wither`
    *   The localized description text for the status effect.
*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/wither.png`
    *   The image file used to represent the wither status icon in the UI.
*   **`display_above_head`**: `0`
    *   The icon will not be displayed above the character's head.
*   **`display_in_hud`**: `1`
    *   The icon will be displayed in the Heads-Up Display (HUD).

### VariableStorageComponent

*   **`name`**: `wither_data`
    *   A component for storing arbitrary data related to the wither effect.
*   **`value_string`**: `""`
    *   An empty string, suggesting this might be used to store dynamic data or flags if needed by the Lua scripts.