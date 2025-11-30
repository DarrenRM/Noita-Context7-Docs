---
title: Explosive Projectile Custom Card
category: entities
---

# Explosive Projectile Custom Card

This document describes the `explosive_projectile.xml` entity, which defines a custom spell card in Noita that imbues projectiles with explosive properties.

## Entity Definition

The `explosive_projectile.xml` entity inherits its core functionality from two base files:

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure and UI elements for a custom spell card.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Contains the specific logic for making projectiles explosive.

## Key Components

### SpriteComponent

This component defines the visual representation of the custom card in the game's UI.

| Attribute    | Value                                     | Description                               |
| :----------- | :---------------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/explosive.png` | Path to the sprite used for the card icon. |

### ItemActionComponent

This component assigns an action ID to the custom card, allowing it to be recognized and used by the game's systems.

| Attribute  | Value              | Description                                                              |
| :--------- | :----------------- | :----------------------------------------------------------------------- |
| `_tags`    | `enabled_in_world` | Ensures the action is available when the player is in the game world.    |
| `action_id`| `EXPLOSIVE_PROJECTILE` | The unique identifier for this spell card's action.                      |