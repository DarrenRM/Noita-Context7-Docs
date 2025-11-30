---
title: Thunder Blast Custom Card
category: entities
---

# Thunder Blast Custom Card

This document describes the `thunder_blast.xml` entity, which defines a custom spell card in Noita.

## Entity Structure

The `thunder_blast.xml` entity is composed of several base entity files and specific components that define its appearance, behavior, and effects.

### Key Components

*   **`Base file="data/entities/base_custom_card.xml"`**: This is the foundational element for all custom spell cards.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the game's UI.
        *   `image_file`: `data/ui_gfx/gun_actions/thunder_blast.png` - Specifies the texture used for the card's icon.
    *   **`ItemActionComponent`**: Links the card to a specific in-game action.
        *   `action_id`: `THUNDER_BLAST` - Identifies the unique action this card triggers.
        *   `_tags="enabled_in_world"`: Indicates the card is usable within the game world.

*   **`Base file="data/entities/misc/custom_cards/base_electricity.xml"`**: Inherits properties related to electrical effects.

*   **`LightComponent`**: Adds a visual light effect when the item is held or identified.
    *   `_tags="enabled_in_hand,item_identified"`: The light is active when the item is in the player's hand or has been identified.
    *   `_enabled="1"`: The light component is active.
    *   `radius`: `40` - The range of the light effect.
    *   `fade_out_time`: `1.5` - How long the light takes to fade.
    *   `r`, `g`, `b`: `20`, `40`, `150` - Defines the color of the light (a bluish hue).

*   **`Base file="data/entities/particles/water_electrocution.xml"`**: Integrates particle effects associated with electrical water interactions.