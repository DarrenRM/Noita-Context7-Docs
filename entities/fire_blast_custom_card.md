---
title: Fire Blast Custom Card
category: entities
---

# Fire Blast Custom Card

This document describes the `fire_blast.xml` entity, which defines a custom spell card in Noita.

## Entity Structure

The `fire_blast.xml` entity inherits from two base files:
*   `data/entities/base_custom_card.xml`: Provides the fundamental structure for custom spell cards, including visual representation and action binding.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Implements the explosive properties of the spell.

## Key Components

### SpriteComponent

This component defines the visual appearance of the spell card in the game's UI.

| Attribute    | Value                               | Description                               |
| :----------- | :---------------------------------- | :---------------------------------------- |
| `image_file` | `data/ui_gfx/gun_actions/fire_blast.png` | Path to the sprite used for the card.     |

### ItemActionComponent

This component links the spell card to a specific in-game action.

| Attribute  | Value      | Description                                                              |
| :--------- | :--------- | :----------------------------------------------------------------------- |
| `_tags`    | `enabled_in_world` | Ensures the action is available when the player is in the game world. |
| `action_id`| `FIRE_BLAST` | The unique identifier for the "Fire Blast" spell action.                 |

## Inheritance

The entity's functionality is extended through inheritance from `base_explosive.xml`, which likely handles the projectile creation, explosion effects, and damage associated with the "Fire Blast" spell.