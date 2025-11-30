---
title: Grenade Trigger Custom Card
category: entities
---

---

# Grenade Trigger Custom Card

This document describes the `grenade_trigger.xml` entity, which defines a custom card in Noita that acts as a grenade trigger.

## Entity Structure

The `grenade_trigger.xml` entity inherits from two base files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental properties of a custom card.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Implements explosive behavior.

## Key Components

### SpriteComponent

This component defines the visual representation of the custom card in the game's UI.

| Attribute    | Value                                     | Description                                     |
| :----------- | :---------------------------------------- | :---------------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/grenade_trigger.png` | Path to the sprite image for the card.          |

### ItemActionComponent

This component assigns an action ID to the custom card, making it usable in the game.

| Attribute   | Value           | Description                                                              |
| :---------- | :-------------- | :----------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world` | Ensures the action is available when the player is in the game world.    |
| `action_id` | `GRENADE_TRIGGER` | The unique identifier for this custom card's action.                     |

## Inheritance

The entity's functionality is built upon the following base files:

*   **`data/entities/base_custom_card.xml`**: This is a foundational file for all custom cards, likely defining common properties like mana cost, cooldown, and other card-specific attributes.
*   **`data/entities/misc/custom_cards/base_explosive.xml`**: This file imparts explosive characteristics to the custom card, meaning it will likely deal damage and create an explosion upon activation.

This setup allows for modular design, where the visual and action aspects are defined here, while the core custom card and explosive mechanics are handled by their respective base files.