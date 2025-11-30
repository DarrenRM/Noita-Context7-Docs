---
title: Firebomb Custom Card
category: entities
---

# Firebomb Custom Card

This document describes the `firebomb.xml` entity, which defines a custom spell card in Noita that functions as a firebomb.

## Entity Structure

The `firebomb.xml` entity inherits from two base files:
*   `data/entities/base_custom_card.xml`: Provides the fundamental structure for custom spell cards.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Implements the explosive behavior for this card.

## Key Components

### SpriteComponent

This component defines the visual representation of the Firebomb card in the game's UI.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/firebomb.png` | Path to the sprite image for the card.    |

### ItemActionComponent

This component assigns an action ID to the card, enabling its functionality within the game.

| Attribute   | Value      | Description                                                               |
| :---------- | :--------- | :------------------------------------------------------------------------ |
| `_tags`     | `enabled_in_world` | Ensures the action is available when the player is in the game world. |
| `action_id` | `FIREBOMB` | The unique identifier for the firebomb action.                            |