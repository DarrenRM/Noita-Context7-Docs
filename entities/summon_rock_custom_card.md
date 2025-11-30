---
title: Summon Rock Custom Card
category: entities
---

# Summon Rock Custom Card

This document describes the `summon_rock.xml` entity, which defines a custom card in Noita that allows the player to summon a rock.

## Base Entity Configuration

The card inherits its base functionality from `base_custom_card.xml`.

### Key Components:

*   **ItemComponent**:
    *   `_tags`: `enabled_in_world`, `enabled_in_hand`, `enabled_in_world` - Indicates the card can be used in various game states.
    *   `is_equipable_forced="1"`: Ensures the item is always equipable.

*   **SpriteComponent (for card icon)**:
    *   `image_file="data/ui_gfx/gun_actions/summon_rock.png"`: Specifies the visual representation of the card on the UI.

*   **ItemActionComponent**:
    *   `action_id="SUMMON_ROCK"`: Assigns a unique identifier for the card's action.

## In-Hand Visuals

This section defines how the item appears when held by the player.

### Key Components:

*   **SpriteComponent (for in-hand)**:
    *   `_tags`: `enabled_in_hand`, `not_enabled_in_wand` - Visible only when held, not when in a wand.
    *   `_enabled="0"`: This component is initially disabled, likely controlled by the `AbilityComponent`.
    *   `offset_x="3"`, `offset_y="6"`: Adjusts the position of the sprite when held.
    *   `image_file="data/items_gfx/in_hand/rock_in_hand.png"`: The image file for the rock when held.

## Ability Configuration

This component defines the core functionality of the custom card.

### Key Components:

*   **AbilityComponent**:
    *   `_tags`: `enabled_in_hand` - The ability is active when the card is held.
    *   `ui_name="$item_rock"`: Sets the display name for the item in the UI (localized).
    *   `entity_file="data/entities/projectiles/deck/rock.xml"`: Specifies the entity file to be spawned when the card is used. This is the "rock" projectile.
    *   `throw_as_item="1"`: The summoned entity is treated as an item that can be thrown.
    *   `simulate_throw_as_item="1"`: Enables simulation of throwing behavior.
    *   `use_entity_file_as_projectile_info_proxy="1"`: Uses the specified `entity_file` to proxy projectile information.

*   **gun_config**:
    *   `deck_capacity="0"`: Indicates this card does not contribute to wand deck capacity.