---
title: Custom Card - Laser
category: data/entities/misc/custom_cards
---

---

# Custom Card - Laser

This document describes the configuration for the "Laser" custom card entity in Noita, intended for AI-assisted modding.

## Entity Structure

The `Laser` entity is built upon two base files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure and functionality for custom cards.
*   `data/entities/misc/custom_cards/base_laser.xml`: Contains specific attributes and behaviors for the laser card.

## Key Components

### SpriteComponent

This component defines the visual representation of the custom card.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/laser.png` | Path to the sprite used for the card icon. |

### ItemActionComponent

This component links the card to a specific in-game action.

| Attribute  | Value | Description                                                              |
| :--------- | :---- | :----------------------------------------------------------------------- |
| `_tags`    | `enabled_in_world` | Ensures the action is available when the player is in the game world. |
| `action_id`| `LASER` | The unique identifier for the laser action.                              |