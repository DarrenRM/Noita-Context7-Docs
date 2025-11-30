---
title: Circle Shot Wand (Custom Card)
category: entities
---

# Circle Shot Wand (Custom Card)

This document describes the configuration for a custom wand entity in Noita, specifically designed to function as a "Circle Shot" spell card.

## Entity Structure

The entity is composed of two primary `Base` components, inheriting functionality from existing game assets.

### Base Components

*   **`data/entities/base_custom_card.xml`**: This base provides the fundamental structure for a custom spell card.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/phantomshot_b.png` - Specifies the sprite used for the card's icon.
    *   **`ItemActionComponent`**: Links the card to a specific in-game action.
        *   `_tags`: `enabled_in_world` - Indicates the card is usable during gameplay.
        *   `action_id`: `CIRCLESHOT_B` - The unique identifier for the spell action this card triggers.

*   **`data/entities/misc/custom_cards/base_laser.xml`**: This base provides particle effects commonly associated with laser-like projectiles.
    *   **`SpriteParticleEmitterComponent`**: Controls the emission of sprite-based particles.
        *   `sprite_file`: `data/particles/shine_blue.xml` - The particle sprite used for visual flair.
        *   `emission_interval_min_frames`: `35`
        *   `emission_interval_max_frames`: `45`
    *   **`ParticleEmitterComponent`**: Controls the emission of material-based particles.
        *   `emitted_material_name`: `plasma_fading` - The material that forms the emitted particles.

## Key Attributes

*   **`action_id`**: `CIRCLESHOT_B` - Crucial for linking the visual card to its functional behavior.
*   **`image_file`**: `data/ui_gfx/gun_actions/phantomshot_b.png` - Determines how the card appears in the player's inventory and spell selection.
*   **`emitted_material_name`**: `plasma_fading` - Defines the visual and potentially physical properties of the projectile's trail or impact.
*   **`sprite_file`** (for particles): `data/particles/shine_blue.xml` - Contributes to the visual aesthetic of the projectile.