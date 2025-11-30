---
title: Heart Better Item Script
category: scripts
---

---

# Heart Better Item Script

This script defines the behavior of the "Heart Better" item in Noita, which enhances the player's maximum health.

## Core Functionality

When the player picks up the "Heart Better" item, the script modifies their `DamageModelComponent` to increase their maximum HP.

### Key Attributes Modified:

*   **`max_hp`**: The player's maximum health is increased by a fixed amount (2) multiplied by a global multiplier (`HEARTS_MORE_EXTRA_HP_MULTIPLIER`).
*   **`max_hp_cap`**: The script respects the player's maximum HP cap, ensuring the health increase does not exceed it.
*   **`max_hp_old`**: Stores the player's maximum HP *before* the increase, useful for logging and potential future logic.
*   **`mLastMaxHpChangeFrame`**: Records the game frame number when the maximum HP was last changed.

## Visual and Audio Effects

Upon pickup, the script triggers visual and audio feedback:

*   **Particles**:
    *   `data/entities/particles/image_emitters/heart_effect.xml`: A visual effect indicating a health gain.
    *   `data/entities/particles/heart_out.xml`: Another visual effect associated with the item.
*   **Sound**: `GameTriggerMusicCue("item")` plays a sound cue.

## Logging and Feedback

The script provides in-game messages to inform the player about the health change:

*   **`GamePrintImportant`**: Displays a message indicating the item was picked up.
*   **`description`**: A detailed log message is generated using `GameTextGet`.
    *   If the health increase was successful, it shows the new total HP (formatted as `math.floor(max_hp*25)`).
    *   If the health increase was blocked by the HP cap, a different message (`$logdesc_heart_blocked`) is displayed.

## Item Removal

After its effects are applied, the item entity is removed from the game using `EntityKill( entity_item )`.

## Global Configuration

*   **`HEARTS_MORE_EXTRA_HP_MULTIPLIER`**: A global variable that can be set to modify the amount of HP gained per "Heart Better" item. Defaults to "1".