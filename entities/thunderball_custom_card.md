---
title: Thunderball Custom Card
category: entities
---

# Thunderball Custom Card

This document describes the Thunderball custom card entity for Noita modding.

## Entity Definition

The Thunderball card is a custom entity that grants the player a unique spell. It inherits functionality from `base_custom_card.xml` and `base_electricity.xml`.

### Key Components

*   **`Base file="data/entities/base_custom_card.xml"`**: Provides the fundamental structure and behavior for custom cards.
    *   **`SpriteComponent`**: Defines the visual representation of the card in the game's UI.
        *   `image_file`: `data/ui_gfx/gun_actions/thunderball.png`
    *   **`ItemActionComponent`**: Assigns an action ID to the card, enabling its functionality.
        *   `action_id`: `THUNDERBALL`
        *   `_tags`: `enabled_in_world` (Indicates the card is usable in the game world)

*   **`Base file="data/entities/misc/custom_cards/base_electricity.xml"`**: Inherits electrical properties and effects.

*   **`LightComponent`**: Adds a visual light effect when the card is held or identified.
    *   `_tags`: `enabled_in_hand,item_identified`
    *   `_enabled`: `1` (The light is active)
    *   `radius`: `40` (The range of the light)
    *   `fade_out_time`: `1.5` (Duration of the light's fade-out)
    *   `r`, `g`, `b`: `20`, `40`, `150` (Color of the light, a bluish hue)

*   **`Base file="data/entities/particles/water_electrocution.xml"`**: Integrates particle effects associated with electrical discharges, likely for visual feedback during spell use.