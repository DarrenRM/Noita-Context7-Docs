---
title: Rainbow Trail Custom Card
category: entities
---

# Rainbow Trail Custom Card

This document describes the `rainbow_trail.xml` entity, which defines a custom card in Noita that creates a rainbow trail effect.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, indicating it's a player-usable item.

### Key Components

*   **`<SpriteComponent>`**:
    *   `image_file`: `data/ui_gfx/gun_actions/rainbow_trail.png` - Specifies the visual icon for this card in the UI.

*   **`<ItemActionComponent>`**:
    *   `_tags`: `enabled_in_world` - This card is active and usable when found in the game world.
    *   `action_id`: `RAINBOW_TRAIL` - A unique identifier for the action this card performs.

*   **`<InheritTransformComponent>`**:
    *   `_tags`: `enabled_in_world,enabled_in_hand` - The visual representation of the card is active both in the world and when held by the player.
    *   **`<Transform>`**:
        *   `position.x`: `5`
        *   `position.y`: `0`
        *   These values define the relative positioning of the card's visual elements.