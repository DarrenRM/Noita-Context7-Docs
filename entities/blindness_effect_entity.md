---
title: Blindness Effect Entity
category: entities
---

# Blindness Effect Entity

This entity defines the visual and auditory effects associated with the "Blindness" status effect in Noita.

## Key Components

### GameEffectComponent
This component governs the core mechanics of the blindness effect.

*   **`effect`**: `BLINDNESS` - Specifies the type of game effect.
*   **`frames`**: `1200` - The duration of the blindness effect in frames (approximately 20 seconds, as 60 frames per second).

### AudioComponent
This component handles the sound associated with the blindness effect.

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound.
*   **`event_root`**: `game_effect/blindness` - The specific audio event to trigger.

### UIIconComponent
This component defines how the blindness status is displayed to the player.

*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/blindness.png` - The image file for the status icon.
*   **`name`**: `$status_blindness` - A localization key for the status name.
*   **`description`**: `$statusdesc_blindness` - A localization key for the status description.
*   **`display_above_head`**: `0` - Indicates the icon is not displayed above the player's head.
*   **`display_in_hud`**: `1` - Indicates the icon is displayed in the Heads-Up Display (HUD).