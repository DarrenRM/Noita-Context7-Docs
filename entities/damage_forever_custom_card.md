---
title: Damage Forever Custom Card
category: entities
---

# Damage Forever Custom Card

This document describes the "Damage Forever" custom card entity for Noita modding. It's designed to be a reusable component for creating custom cards with a specific damage-over-time effect.

## Entity Structure

The `Damage Forever` entity is built upon two base entities:

*   `data/entities/base_custom_card.xml`: Provides the fundamental structure and functionality for custom cards, including sprite and action components.
*   `data/entities/misc/custom_cards/base_damage.xml`: Likely contains the core logic for applying damage, which this card inherits and modifies.

## Key Components

### SpriteComponent

This component defines the visual representation of the custom card in the game's UI.

*   `image_file`: Specifies the texture used for the card's icon.
    *   `data/ui_gfx/gun_actions/damage_forever.png`

### ItemActionComponent

This component links the card to a specific in-game action.

*   `_tags`: Determines when the action is available.
    *   `enabled_in_world`: The action is available when the player is in the game world.
*   `action_id`: A unique identifier for the action.
    *   `DAMAGE_FOREVER`

## Inheritance

The `Damage Forever` card inherits its core functionality from `base_damage.xml`. This implies that the damage-over-time effect is defined within that base file, and this custom card simply provides a specific UI representation and action ID for it.

## Usage in Modding

To use this custom card in your Noita mod:

1.  **Place the entity file:** Ensure the `damage_forever.xml` file is correctly placed within your mod's `data/entities/misc/custom_cards/` directory.
2.  **Reference in other entities:** You can then reference this entity in other XML files (e.g., to add it to a wand, a chest, or as a spell drop) using its entity name.
3.  **Customization:** If you need to alter the damage amount, duration, or other damage-related properties, you would typically modify the `base_damage.xml` file or create a new base damage entity to inherit from.