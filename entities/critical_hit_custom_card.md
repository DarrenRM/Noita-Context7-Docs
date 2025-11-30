---
title: Critical Hit Custom Card
category: entities
---

# Critical Hit Custom Card

This document describes the `critical_hit.xml` entity, which defines a custom card in Noita that grants a critical hit effect.

## Entity Structure

The `Critical Hit` entity is composed of two base entity files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental properties of a custom card, including its visual representation and interaction components.
*   `data/entities/misc/custom_cards/base_damage.xml`: Likely contributes to the damage-modifying aspects of the card.

## Key Components

### SpriteComponent

This component defines the visual appearance of the custom card in the game's UI.

| Attribute    | Value                                 | Description                               |
| :----------- | :------------------------------------ | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/critical_hit.png` | Path to the sprite used for the card. |

### ItemActionComponent

This component assigns an action ID to the custom card, enabling its functionality within the game.

| Attribute   | Value       | Description                                                              |
| :---------- | :---------- | :----------------------------------------------------------------------- |
| `_tags`     | `enabled_in_world` | Specifies that this action is available when the player is in the world. |
| `action_id` | `CRITICAL_HIT` | The unique identifier for the critical hit action.                       |