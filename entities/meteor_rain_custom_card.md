---
title: Meteor Rain Custom Card
category: entities
---

# Meteor Rain Custom Card

This document describes the `meteor_rain.xml` entity, which defines a custom card in Noita that triggers a meteor shower effect.

## Entity Definition

The `meteor_rain.xml` entity is composed of two base entity definitions:

*   **`data/entities/base_custom_card.xml`**: This base provides the fundamental properties of a custom card, including its visual representation and interaction components.
*   **`data/entities/misc/custom_cards/base_explosive.xml`**: This base likely contributes to the explosive nature or impact effects associated with the meteor shower.

## Key Components

### SpriteComponent

This component defines the visual asset used for the custom card in the game's UI.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/meteor_rain.png` | The image file used to represent the "Meteor Rain" card in the UI. |

### ItemActionComponent

This component defines the action associated with the custom card when it's used by the player.

| Attribute   | Value        | Description                                                                 |
| :---------- | :----------- | :-------------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world` | Indicates that this action can only be activated when the player is in the game world. |
| `action_id` | `METEOR_RAIN` | A unique identifier for the "Meteor Rain" action.                           |

## Summary

The `meteor_rain.xml` entity is a straightforward definition for a custom card. It leverages existing base entities to provide the visual representation of the card in the UI and to link it to a specific in-game action, `METEOR_RAIN`, which is likely implemented in other game files. The `base_explosive.xml` suggests that the meteor rain effect will have explosive properties.