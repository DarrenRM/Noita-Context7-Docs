---
title: Teleportation Effect Entity
category: entities
---

# Teleportation Effect Entity

This entity defines the visual and functional aspects of the teleportation status effect applied to enemies in Noita.

## Key Components

### Base Entity
*   **`data/entities/particles/teleportation_blast.xml`**: Inherits visual effects from a pre-defined teleportation blast particle system.

### SpriteParticleEmitterComponent
*   **`randomize_position_inside_hitbox="1"`**: Ensures the teleportation particles are emitted randomly within the entity's hitbox, creating a more dynamic visual.

### GameEffectComponent
This is the core component that governs the teleportation effect's behavior.
*   **`effect="TELEPORTATION"`**: Specifies the type of game effect.
*   **`frames="320"`**: The total duration of the effect in game frames.
*   **`teleportation_probability="200"`**: A value (likely out of 255 or 1000, needs context) that determines the chance of teleportation occurring. Higher values mean a higher probability.
*   **`teleportation_delay_min_frames="140"`**: The minimum number of frames that must pass before a teleportation attempt can be made.

### UIIconComponent
This component defines how the teleportation status is displayed to the player.
*   **`icon_sprite_file="data/ui_gfx/status_indicators/teleportation.png"`**: The image file used for the status icon.
*   **`name="$status_teleportation"`**: A localization key for the status effect's name.
*   **`description="$statusdesc_teleportation"`**: A localization key for the status effect's description.
*   **`display_above_head="0"`**: Indicates the icon is not displayed above the affected entity's head.
*   **`display_in_hud="1"`**: Indicates the icon is displayed in the player's Heads-Up Display (HUD).
*   **`is_perk="0"`**: Marks this as a status effect, not a player perk.