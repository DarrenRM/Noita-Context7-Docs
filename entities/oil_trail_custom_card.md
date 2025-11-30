---
title: Oil Trail Custom Card
category: entities
---

# Oil Trail Custom Card

This document describes the `oil_trail.xml` entity, which defines a custom card in Noita that creates an oil trail when used.

## Key Components

### Base Entity

The core of this custom card is built upon `base_custom_card.xml`.

*   **SpriteComponent**:
    *   `image_file`: `data/ui_gfx/gun_actions/oil_trail.png` - This specifies the visual representation of the card in the UI.

*   **ItemActionComponent**:
    *   `_tags`: `enabled_in_world` - Indicates the action is available when the item is in the game world.
    *   `action_id`: `OIL_TRAIL` - A unique identifier for this specific action.

### Inheritance and Transformation

*   **InheritTransformComponent**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The transformation applies when the item is in the world or held by the player.
    *   **Transform**:
        *   `position.x`: `5` - Offsets the visual position of the card's sprite in the UI.
        *   `position.y`: `0` - No vertical offset.