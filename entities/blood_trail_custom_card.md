---
title: Blood Trail Custom Card
category: entities
---

# Blood Trail Custom Card

This document describes the `blood_trail.xml` entity, which defines a custom card in Noita that creates a blood trail effect.

## Entity Definition

The `blood_trail.xml` entity is a custom card designed to be used within the game.

### Base Entity

*   **`Base file="data/entities/base_custom_card.xml"`**: This indicates that the entity inherits its core functionality from the `base_custom_card.xml` file, providing standard custom card behaviors.

### Sprite Component

*   **`SpriteComponent`**: This component defines the visual representation of the custom card.
    *   **`image_file="data/ui_gfx/gun_actions/blood_trail.png"`**: Specifies the image used for the card's icon in the user interface.

### Item Action Component

*   **`ItemActionComponent`**: This component defines the action associated with the custom card when it's used.
    *   **`_tags="enabled_in_world"`**: The action is enabled when the card is present in the game world.
    *   **`action_id="BLOOD_TRAIL"`**: This is the unique identifier for the action this card performs.

### Inherit Transform Component

*   **`InheritTransformComponent`**: This component handles the positioning and transformation of the entity.
    *   **`_tags="enabled_in_world,enabled_in_hand"`**: The transform is applied when the card is in the world or held by the player.
    *   **`Transform position.x="5" position.y="0"`**: Defines a slight offset for the entity's position.