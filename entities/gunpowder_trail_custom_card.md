---
title: Gunpowder Trail Custom Card
category: entities
---

# Gunpowder Trail Custom Card

This document describes the `gunpowder_trail.xml` entity, which defines a custom card in Noita that creates a gunpowder trail effect.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, indicating it's intended to be a player-usable item.

### Key Components

*   **`<Base>`**:
    *   **`<SpriteComponent>`**:
        *   `image_file`: `data/ui_gfx/gun_actions/gunpowder_trail.png` - Specifies the visual representation of the card on the UI.
    *   **`<ItemActionComponent>`**:
        *   `_tags`: `enabled_in_world` - This action is available when the player is in the game world.
        *   `action_id`: `GUNPOWDER_TRAIL` - A unique identifier for this specific item action.

*   **`<InheritTransformComponent>`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - The transform properties are applied when the item is in the world or held by the player.
    *   **`<Transform>`**:
        *   `position.x`: `5` - Offsets the visual position of the card's sprite in the UI.
        *   `position.y`: `0` - Offsets the visual position of the card's sprite in the UI.

This entity primarily defines the visual and functional aspects of the "Gunpowder Trail" custom card, allowing it to be recognized and used as an item action within the game.