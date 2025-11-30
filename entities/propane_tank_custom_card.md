---
title: Propane Tank Custom Card
category: entities
---

# Propane Tank Custom Card

This document describes the `propane_tank.xml` entity, which defines a custom card in Noita that functions as a propane tank.

## Base Entity Configuration

The propane tank card inherits its base functionality from `base_custom_card.xml`.

### Key Components:

*   **`ItemComponent`**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand` - Indicates the item can be interacted with both in the world and when held.
    *   `is_equipable_forced`: `1` - Forces the item to be equipable.

*   **`SpriteComponent` (for UI/World)**:
    *   `image_file`: `data/ui_gfx/gun_actions/propane_tank.png` - Specifies the image used for the card in the UI and potentially in the world.

*   **`ItemActionComponent`**:
    *   `_tags`: `enabled_in_world` - The action is active when the item is in the world.
    *   `action_id`: `PROPANE_TANK` - A unique identifier for this item's action.

## In-Hand Visuals

This section defines how the propane tank appears when held by the player.

### Key Components:

*   **`SpriteComponent` (for Hand)**:
    *   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` - Visible when held, but cannot be placed on a wand.
    *   `_enabled`: `0` - This sprite is initially disabled, likely controlled by the `AbilityComponent`.
    *   `offset_x`: `3.5`
    *   `offset_y`: `6`
    *   `image_file`: `data/items_gfx/in_hand/propane_tank_in_hand.png` - The specific sprite for the propane tank when held.

## Ability and Throwing Mechanics

This component governs the behavior of the propane tank when used as a card.

### Key Components:

*   **`AbilityComponent`**:
    *   `_tags`: `enabled_in_hand` - The ability is active when the item is held.
    *   `ui_name`: `Propane tank` - The name displayed in the user interface.
    *   `entity_file`: `data/entities/projectiles/propane_tank.xml` - Specifies the entity file to be spawned when the ability is used (this is the actual projectile).
    *   `rotate_hand_amount`: `0.05` - Controls the rotation of the player's hand when using the item.
    *   `throw_as_item`: `1` - The item is thrown as a projectile.
    *   `simulate_throw_as_item`: `1` - Simulates the throwing behavior.
    *   `use_entity_file_as_projectile_info_proxy`: `1` - Uses the `entity_file` to proxy projectile information.

    *   **`gun_config`**:
        *   `deck_capacity`: `0` - Indicates this item does not contribute to wand deck capacity.