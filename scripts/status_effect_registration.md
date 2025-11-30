---
title: Status Effect Registration
category: scripts
---

---

# Status Effect Registration

This script registers status effects within Noita, making them available for use in the game. It iterates through a predefined list of status effects and registers each one with its associated properties.

## Key Attributes for Status Effect Registration

The `GameRegisterStatusEffect` function takes several arguments to define a status effect. The most important ones are:

*   **`effect.id`**: A unique identifier for the status effect.
*   **`effect.ui_name`**: The name displayed to the player in the UI.
*   **`effect.ui_description`**: A description of the status effect shown to the player.
*   **`effect.ui_icon`**: The icon representing the status effect in the UI.
*   **`effect.protects_from_fire`**: (Boolean) Whether this effect protects the player from fire damage.
*   **`effect.remove_cells_that_cause_when_activated`**: (Boolean) If true, certain cells might be removed when this effect is activated.
*   **`effect.effect_entity`**: The entity ID associated with the visual or functional effect of the status.
*   **`effect.min_threshold_normalized`**: A normalized threshold value (0.0 to 1.0) that might influence the effect's potency or activation.
*   **`effect.effect_permanent`**: (Boolean) If true, the status effect will not expire naturally.
*   **`effect.is_harmful`**: (Boolean) Indicates if the status effect is detrimental to the player.
*   **`effect.ui_timer_offset_normalized`**: A normalized offset for the status effect's timer display.

## Registration Process

The script first loads the `status_list.lua` file, which contains the definitions for various status effects. It then loops through each `effect` in the `status_effects` table and calls `GameRegisterStatusEffect` with the relevant properties. Default values (like `false` or `0.0`) are provided for optional parameters if they are not defined in the `status_effects` table.