---
title: Status Effect - Weaken
category: entities
---

# Status Effect - Weaken

This entity defines the "Weaken" status effect in Noita, primarily managed through Lua scripts that apply debuffs to entities.

## Key Components

### LuaComponent
This component is central to the functionality of the status effect, executing Lua scripts at specific intervals or when the effect is applied/removed.

*   **`script_source_file`**: Specifies the Lua script to execute.
    *   `data/scripts/status_effects/weaken_start.lua`: Executes when the Weaken effect begins.
    *   `data/scripts/status_effects/weaken_end.lua`: Executes when the Weaken effect ends.
    *   `data/scripts/status_effects/wither_start.lua`: Executes when the Wither effect (often associated with Weaken) begins.
    *   `data/scripts/status_effects/wither_end.lua`: Executes when the Wither effect ends.
*   **`execute_every_n_frame`**: Determines how often the script runs (e.g., `4` for every 4 frames). A value of `-1` typically means it runs only once on execution.
*   **`remove_after_executed`**: If `1`, the Lua component is removed after its script has executed.
*   **`execute_on_removed`**: If `1`, the script will execute when the entity or component is removed.

### LifetimeComponent
Manages how long the status effect persists.

*   **`lifetime`**: The duration of the effect in frames. `1200` frames is equivalent to 20 seconds (since 60 frames = 1 second).

### UIIconComponent
Defines how the status effect is represented in the game's user interface.

*   **`name`**: The internal name for the UI element, often linked to localization strings (e.g., `$status_weaken_combined`).
*   **`description`**: The localized description displayed to the player (e.g., `$statusdesc_weaken_combined`).
*   **`icon_sprite_file`**: The path to the sprite used for the status icon (e.g., `data/ui_gfx/status_indicators/scared.png`).
*   **`is_perk`**: Indicates if this is a perk (`0` means it's a status effect).
*   **`display_above_head`**: Whether the icon appears above the entity's head (`0` means no).
*   **`display_in_hud`**: Whether the icon appears in the player's HUD (`1` means yes).

### VariableStorageComponent
Allows storing custom data associated with the entity.

*   **`name`**: The name of the variable (e.g., `wither_data`).
*   **`value_string`**: An initial string value for the variable. This can be used by Lua scripts to store or retrieve state related to the effect.

## Summary

The `effect_weaken.xml` entity primarily acts as a container for Lua scripts that implement the logic for the "Weaken" and "Wither" status effects. It defines their duration and how they are visually represented in the UI. The actual debuffing mechanics are handled within the associated Lua scripts.