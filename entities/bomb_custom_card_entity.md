---
title: Bomb Custom Card Entity
category: entities
---

# Bomb Custom Card Entity

This document describes the Noita entity configuration for the "Bomb" custom card, commonly found in the game's data files. This entity defines how the bomb item behaves when picked up, equipped, and used.

## Key Components and Attributes

The `Bomb.xml` entity is structured using several key components that dictate its functionality:

### Base Entity (`<Base>`)

This component inherits core properties from `base_custom_card.xml`, providing a foundation for item-like behavior.

*   **`<ItemComponent>`**:
    *   `_tags="enabled_in_world,enabled_in_hand,enabled_in_world"`: Specifies that this item can exist and be interacted with in the game world and when held by the player.
    *   `is_equipable_forced="1"`: Ensures the item is always equipable.

*   **`<SpriteComponent>` (for world/inventory)**:
    *   `image_file="data/ui_gfx/gun_actions/bomb.png"`: Defines the visual representation of the bomb card in the game's UI and inventory.

*   **`<ItemActionComponent>`**:
    *   `_tags="enabled_in_world"`: Links this item to world interactions.
    *   `action_id="BOMB"`: Assigns a unique identifier for the bomb action.

### In-Hand Sprite (`<SpriteComponent>`)

This component defines the visual appearance of the bomb when it's held by the player.

*   **`<SpriteComponent>`**:
    *   `_tags="enabled_in_hand,not_enabled_in_wand"`: Indicates this sprite is only visible when the item is held and not when part of a wand.
    *   `_enabled="0"`: This sprite is initially disabled, likely controlled by the `AbilityComponent`.
    *   `offset_x="3.5"`, `offset_y="6"`: Adjusts the position of the sprite relative to the player's hand.
    *   `image_file="data/items_gfx/in_hand/bomb_in_hand.png"`: The specific image file for the bomb when held.

### Ability Component (`<AbilityComponent>`)

This is the core component that defines the bomb's functional behavior as an actionable item.

*   **`<AbilityComponent>`**:
    *   `_tags="enabled_in_hand"`: This ability is active when the item is held.
    *   `ui_name="$action_bomb"`: Sets the display name for the action in the UI, referencing a localization string.
    *   `entity_file="data/entities/projectiles/bomb.xml"`: Crucially, this specifies the entity file that will be spawned when the bomb is used, defining the actual projectile behavior.
    *   `rotate_hand_amount="0.05"`: Controls a slight rotation of the player's hand when using the item.
    *   `throw_as_item="1"`: Indicates the bomb is thrown like a physical item.
    *   `simulate_throw_as_item="1"`: Enables simulation of throwing behavior.
    *   `use_entity_file_as_projectile_info_proxy="1"`: Uses the projectile entity's properties as a proxy for information.

*   **`<gun_config>`**:
    *   `deck_capacity="0"`: This bomb card does not contribute to wand deck capacity.

---