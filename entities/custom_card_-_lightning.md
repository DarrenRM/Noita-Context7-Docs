---
title: Custom Card - Lightning
category: entities
---

---

# Custom Card - Lightning

This document describes the configuration for the "Lightning" custom card in Noita, focusing on its visual representation, action, and associated effects.

## Entity Structure

The `Lightning` entity is composed of several base components and specific configurations:

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
    *   **`SpriteComponent`**: Defines the visual appearance of the card in the game.
        *   `image_file`: `data/ui_gfx/gun_actions/lightning.png` - Specifies the texture used for the card's icon.
    *   **`ItemActionComponent`**: Assigns an action ID to the card.
        *   `action_id`: `LIGHTNING` - This ID is used by the game to trigger the card's specific effect.
        *   `_tags`: `enabled_in_world` - Indicates the card is active and usable within the game world.

*   **`Base file="data/entities/misc/custom_cards/base_electricity.xml"`**: Inherits electrical properties and behaviors. This likely provides the underlying mechanics for electrical damage and effects.

*   **`LightComponent`**: Adds a light source when the card is held or identified.
    *   `_tags`: `enabled_in_hand,item_identified` - The light is active when the player is holding the card or has identified it.
    *   `_enabled`: `1` - The light component is active.
    *   `radius`: `40` - The radius of the light emitted.
    *   `fade_out_time`: `1.5` - The duration in seconds for the light to fade out.
    *   `r`, `g`, `b`: `20`, `40`, `150` - Defines the color of the light (a bluish hue).

*   **`Base file="data/entities/particles/water_electrocution.xml"`**: Inherits particle effects related to electrocution, likely for visual feedback when the lightning effect is active.