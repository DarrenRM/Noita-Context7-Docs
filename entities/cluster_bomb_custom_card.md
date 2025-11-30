---
title: Cluster Bomb Custom Card
category: entities
---

# Cluster Bomb Custom Card

This document describes the configuration for the "Cluster Bomb" custom card entity in Noita, intended for AI-assisted modding.

## Entity Structure

The `Cluster Bomb` entity inherits from `base_custom_card.xml` and `base_explosive.xml`, combining the functionality of a custom card with explosive properties.

### Base Components

*   **`Base file="data/entities/base_custom_card.xml"`**: This establishes the entity as a custom card, providing its fundamental card-like behavior and UI representation.
    *   **`SpriteComponent`**: Defines the visual appearance of the card in the game's UI.
        *   `image_file`: `data/ui_gfx/gun_actions/clusterbomb.png` - Specifies the texture used for the card's icon.
    *   **`ItemActionComponent`**: Links the card to a specific in-game action.
        *   `_tags="enabled_in_world"`: Ensures the action is available when the player is in the game world.
        *   `action_id="CLUSTERMOD"`: Identifies the unique action associated with this card.

*   **`Base file="data/entities/misc/custom_cards/base_explosive.xml"`**: This component imbues the custom card with explosive characteristics, likely defining its projectile behavior and explosion effects. The specific details of this base file are not provided in the source snippet but are crucial for the card's explosive functionality.