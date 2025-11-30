---
title: Custom Card - Grenade
category: entities
---

# Custom Card - Grenade

This document describes the `grenade.xml` entity, which defines a custom card in Noita that functions as a grenade.

## Entity Structure

The `grenade.xml` entity inherits from two base files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure for custom cards, including visual representation and item action capabilities.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Implements the explosive properties of the card.

## Key Components

### SpriteComponent

This component defines the visual appearance of the grenade card in the game's UI.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/grenade.png` | Path to the sprite used for the card.     |

### ItemActionComponent

This component assigns an action ID to the card, enabling its use as an item.

| Attribute   | Value     | Description                                                              |
| :---------- | :-------- | :----------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world` | Ensures the action is available when the player is in the game world. |
| `action_id` | `GRENADE` | The unique identifier for the grenade action.                            |

## Inheritance

The `grenade.xml` entity leverages inheritance to combine functionality:

*   **`base_custom_card.xml`**: Provides the framework for custom cards, including how they are displayed and interacted with as items.
*   **`base_explosive.xml`**: Implements the core logic for explosive entities, such as damage, radius, and explosion effects.