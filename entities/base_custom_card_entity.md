---
title: Base Custom Card Entity
category: entities
---

# Base Custom Card Entity

This document describes the base entity definition for custom cards in Noita, serving as a template for creating new spell cards.

## Core Components

The `card` entity is built upon several fundamental components that define its behavior and appearance.

### `ItemComponent`

Handles the item-specific properties of the card.

*   **`preferred_inventory`**: Specifies where the item is best suited in the inventory. `FULL` indicates it takes up a full slot.

### `HitboxComponent`

Defines the physical collision area of the card.

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Define the bounding box dimensions for collision detection.

### `SimplePhysicsComponent`

Enables basic physics interactions for the card.

### `VelocityComponent`

Allows the card to have velocity, enabling movement.

### `SpriteComponent`

Manages the visual representation of the card. Multiple `SpriteComponent` instances are used to handle different states:

*   **`item_identified`**: The sprite displayed when the card is identified and ready for use.
    *   `image_file`: `data/ui_gfx/gun_actions/empty.png` (default, can be overridden)
    *   `offset_x`, `offset_y`: Adjusts the sprite's position.
    *   `z_index`: Controls the sprite's layering.
*   **`item_unidentified`**: The sprite displayed when the card is unidentified.
    *   `image_file`: `data/ui_gfx/gun_actions/unidentified.png`
*   **`item_bg`**: The background sprite for the card in the inventory.
    *   `image_file`: `data/ui_gfx/inventory/item_bg_projectile.png`

### `SpriteOffsetAnimatorComponent`

Adds a subtle bobbing animation to the card's sprites.

*   **`y_amount`**: The maximum vertical displacement of the animation.
*   **`y_speed`**: The speed at which the animation plays.
*   **`sprite_id`**: Links the animator to a specific `SpriteComponent` (0-indexed).

### `ItemActionComponent`

Links the card to a specific action or spell.

*   **`action_id`**: This is a crucial field that must be set to the ID of the spell or action this card represents.

## Key Attributes for Modding

When creating custom cards, focus on these attributes:

*   **`ItemActionComponent.action_id`**: This is the most important attribute to define what spell the card casts.
*   **`SpriteComponent.image_file`**: Customize the visual appearance of the card for both identified and unidentified states.
*   **`HitboxComponent`**: Adjust collision bounds if necessary for unique card interactions.
*   **`SpriteOffsetAnimatorComponent`**: Fine-tune the bobbing animation for visual appeal.