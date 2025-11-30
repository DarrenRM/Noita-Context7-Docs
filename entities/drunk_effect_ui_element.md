---
title: Drunk Effect UI Element
category: entities
---

# Drunk Effect UI Element

This entity defines the visual and functional components for the "Drunk" status effect in Noita, specifically how it's represented in the UI.

## Key Components

### `Base` (Inherited)

This entity inherits from `data/entities/particles/drunk.xml`. This implies it utilizes the particle system defined there for visual effects associated with the drunk status.

### `SpriteParticleEmitterComponent`

This component, inherited from the base, controls the emission of particles.

*   **`emission_interval_min_frames`**: `20` - The minimum number of frames between particle emissions.
*   **`emission_interval_max_frames`**: `50` - The maximum number of frames between particle emissions.
*   **`randomize_position_inside_hitbox`**: `0` - Particles are not randomized within the hitbox; their position is likely more controlled.

### `GameEffectComponent`

This component applies the actual game effect.

*   **`effect`**: `DRUNK` - Specifies the type of game effect being applied.
*   **`frames`**: `1200` - The duration of the effect in frames (approximately 20 seconds).

### `UIIconComponent`

This component handles the display of the status effect in the user interface.

*   **`name`**: `$status_drunk_ui` - The internal name for the UI element, likely linked to localization for the status name.
*   **`description`**: `$statusdesc_drunk_ui` - The internal name for the UI element's description, likely linked to localization for the status description.
*   **`icon_sprite_file`**: `data/ui_gfx/status_indicators/alcoholic.png` - The sprite file used for the status icon in the UI.
*   **`is_perk`**: `0` - Indicates this is not a perk.
*   **`display_above_head`**: `0` - The icon does not display above the player's head.
*   **`display_in_hud`**: `1` - The icon is displayed in the Heads-Up Display (HUD).