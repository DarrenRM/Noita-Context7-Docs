---
title: TNT Custom Card
category: entities
---

# TNT Custom Card

This document details the configuration for the "TNT" custom card entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of this entity is based on `base_custom_card.xml`, providing fundamental properties for custom cards.

### Key Components

*   **`ItemComponent`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - Indicates the card can be used both in the world and when held.
    *   `is_equipable_forced="1"`: Ensures the item is always equipable.

*   **`SpriteComponent` (Base)**:
    *   `image_file="data/ui_gfx/gun_actions/dynamite.png"`: Defines the visual representation of the card in the UI.

*   **`ItemActionComponent`**:
    *   `action_id="DYNAMITE"`: Assigns a unique identifier for this action.

*   **`SpriteComponent` (In Hand)**:
    *   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` - Specifies this sprite is only visible when the item is held and not on a wand.
    *   `_enabled="0"`: This sprite is initially disabled, likely controlled by other components.
    *   `offset_x="2.5"`, `offset_y="4.5"`: Adjusts the sprite's position when held.
    *   `image_file="data/items_gfx/in_hand/tnt_in_hand.png"`: The visual asset for the TNT card when held.

*   **`AbilityComponent`**:
    *   `_tags`: `enabled_in_hand` - This ability is active when the card is held.
    *   `ui_name="$action_high_explosive"`: Sets the display name for the action (localized).
    *   `entity_file="data/entities/projectiles/tnt.xml"`: Crucially, this links the card to the actual TNT projectile entity that will be spawned.
    *   `rotate_hand_amount="0.05"`: Introduces a slight rotation when throwing.
    *   `throw_as_item="1"`: The projectile is thrown as if it were an item.
    *   `simulate_throw_as_item="1"`: Enables simulation of throwing as an item.
    *   `use_entity_file_as_projectile_info_proxy="1"`: Uses the projectile entity's properties for proxy information.
    *   **`gun_config`**:
        *   `deck_capacity="0"`: Indicates this card does not contribute to wand deck capacity.

This configuration effectively creates a custom card that, when used, throws a TNT projectile.