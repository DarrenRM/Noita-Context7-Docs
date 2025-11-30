---
title: Fireball Custom Card
category: entities
---

---

# Fireball Custom Card

This document describes the configuration for the "Fireball" custom spell card in Noita, intended for AI-assisted modding.

## Entity Definition

The `Fireball` entity is defined by an XML file that inherits from base entity configurations.

### Base Files

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure and UI elements for a custom spell card.
    *   **SpriteComponent**: Defines the visual representation of the card in the UI.
        *   `image_file`: `data/ui_gfx/gun_actions/fireball.png` - Specifies the texture for the card's icon.
    *   **ItemActionComponent**: Links the card to a specific in-game action.
        *   `_tags`: `enabled_in_world` - Indicates the card is usable during gameplay.
        *   `action_id`: `FIREBALL` - The unique identifier for the fireball spell action.
*   `data/entities/misc/custom_cards/base_explosive.xml`: Inherits properties related to explosive effects, likely defining the projectile's behavior and damage.

## Key Attributes

The primary attributes defining this custom card are its visual representation in the UI and its association with the `FIREBALL` action, which is further enhanced by the `base_explosive.xml` configuration.