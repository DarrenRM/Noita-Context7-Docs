---
title: Water Trail Custom Card
category: entities
---

# Water Trail Custom Card

This document describes the `water_trail.xml` entity, which defines a custom card in Noita that creates a water trail effect.

## Entity Definition

The `water_trail.xml` entity is a custom card designed to be used within the game.

### Base Entity

*   **`base_custom_card.xml`**: This entity inherits its core functionality from `base_custom_card.xml`, indicating it's a player-usable item with card-like properties.

### Sprite Component

*   **`SpriteComponent`**: Defines the visual representation of the custom card.
    *   **`image_file`**: `data/ui_gfx/gun_actions/water_trail.png` - Specifies the image used for the card's icon in the UI.

### Item Action Component

*   **`ItemActionComponent`**: Handles the in-game action associated with this card.
    *   **`_tags`**: `enabled_in_world` - The action is active when the item is in the game world.
    *   **`action_id`**: `WATER_TRAIL` - A unique identifier for this specific action.

### Inherit Transform Component

*   **`InheritTransformComponent`**: Manages the positioning and transformation of the entity.
    *   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The transform is applied when the entity is in the world and held by the player.
    *   **`Transform`**:
        *   **`position.x`**: `5` - Offsets the entity 5 units to the right.
        *   **`position.y`**: `0` - No vertical offset.