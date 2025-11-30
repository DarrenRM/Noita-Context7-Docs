---
title: High Explosive Custom Card
category: entities
---

# High Explosive Custom Card

This document describes the configuration for the "High Explosive" custom card entity in Noita, intended for AI-assisted modding.

## Entity Definition

The `High Explosive` card is a custom entity that grants the player a powerful explosive effect.

### Key Components:

*   **`Base file="data/entities/base_custom_card.xml"`**: Inherits core functionality for custom cards.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/high_explosive.png` - Specifies the sprite used for the card icon.
    *   **`ItemActionComponent`**: Links the card to a specific in-game action.
        *   `action_id`: `HIGH_EXPLOSIVE` - Identifies the unique action this card triggers.
        *   `_tags="enabled_in_world"`: Ensures the action is available when the player is in the game world.

*   **`Base file="data/entities/misc/custom_cards/base_high_explosive.xml"`**: This likely includes the actual logic and effects associated with the "High Explosive" action, such as projectile behavior, damage, and explosion radius. (Details not provided in the source XML).

*   **`LightComponent`**: Adds a visual light effect when the card is held or identified.
    *   `_tags="enabled_in_hand,item_identified"`: Activates the light when the item is in hand and identified.
    *   `_enabled="1"`: Ensures the light component is active.
    *   `radius`: `20` - The range of the light.
    *   `fade_out_time`: `1.5` - How long the light takes to fade.
    *   `r`, `g`, `b`: `80`, `60`, `10` - Defines the color of the light (a warm, orange-ish hue).