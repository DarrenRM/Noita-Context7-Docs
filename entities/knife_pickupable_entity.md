---
title: Knife Pickupable Entity
category: entities
---

# Knife Pickupable Entity

This document describes the `knife_pickupable.xml` entity, which defines a throwable knife item in Noita.

## Core Components

This entity utilizes several core components to define its physical properties, behavior, and item-specific attributes.

### Physics Components

These components govern the physical interaction of the knife within the game world.

*   **`PhysicsBodyComponent`**:
    *   `uid`: Unique identifier for the physics body.
    *   `allow_sleep`: Allows the body to enter a sleep state when inactive to save performance.
    *   `is_bullet`: Indicates this physics body is treated as a projectile.
    *   `send_collision_messages`: Enables collision event notifications.
    *   `on_death_leave_physics_body`: Ensures the physics body persists even if the entity is destroyed.

*   **`PhysicsImageShapeComponent`**:
    *   `body_id`: Links this shape to a specific `PhysicsBodyComponent`.
    *   `image_file`: Specifies the visual sprite for the knife's physical representation (`data/items_gfx/knife.png`).
    *   `material`: Defines the physical material properties (`rock_box2d_nohit_hard`).

*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed`: The maximum velocity the knife can achieve when thrown.
    *   `throw_force_coeff`: A coefficient influencing the force applied during a throw.
    *   `attach_to_surfaces_knife_style`: Enables a specific throwing behavior where the knife can stick to surfaces.
    *   `min_torque`, `max_torque`: Defines the range of rotational force applied when thrown.

*   **`ProjectileComponent`**:
    *   `lifetime`: How long the projectile exists before despawning (-1 means it persists indefinitely or until other conditions are met).
    *   `penetrate_entities`: Allows the projectile to pass through other entities.

*   **`VelocityComponent`**:
    *   Defines the initial velocity of the entity.

### Item Components

These components define the knife as an item that can be picked up, equipped, and used.

*   **`SpriteComponent`**:
    *   `_tags="enabled_in_hand"`: This sprite is active when the item is held by the player.
    *   `_enabled="0"`: This sprite is initially disabled, likely meaning the in-hand sprite is loaded separately or activated on equip.
    *   `offset_x`, `offset_y`: Adjusts the position of the sprite when held.
    *   `image_file`: The sprite used when the knife is in the player's hand (`data/items_gfx/in_hand/knife_in_hand.png`).

*   **`ItemComponent`**:
    *   `item_name`: The display name of the item ("Throwing knife").
    *   `is_pickable`: Allows the player to pick up the item.
    *   `is_equipable_forced`: The item is automatically equipped when picked up.
    *   `ui_sprite`: The icon displayed in the UI (`data/ui_gfx/items/knife.png`).
    *   `ui_description`: A short description for the UI ("Equip and throw.").
    *   `preferred_inventory`: Suggests the inventory slot for this item ("QUICK").

*   **`AbilityComponent`**:
    *   `ui_name`: The name displayed in ability-related UI elements ("Throwing knife").
    *   `throw_as_item`: Indicates this ability is related to throwing the item.
    *   `gun_config`:
        *   `deck_capacity`: Set to 0, suggesting it doesn't use a wand deck.

*   **`UIInfoComponent`**:
    *   `name`: The name displayed in UI tooltips or information panels ("Throwing knife").

## Key Attributes Summary

| Component Type          | Key Attribute(s)                                                              | Description                                                                                             |
| :---------------------- | :---------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `PhysicsBodyComponent`  | `is_bullet`, `send_collision_messages`                                        | Defines the entity as a projectile with collision detection.                                            |
| `PhysicsImageShapeComponent` | `image_file`, `material`                                                      | Sets the visual appearance and physical properties of the knife.                                        |
| `PhysicsThrowableComponent` | `max_throw_speed`, `throw_force_coeff`, `attach_to_surfaces_knife_style`      | Controls how the knife is thrown and its interaction with surfaces.                                     |
| `ProjectileComponent`   | `penetrate_entities`                                                          | Allows the knife to pass through other game entities.                                                   |
| `ItemComponent`         | `item_name`, `is_pickable`, `is_equipable_forced`, `ui_description`           | Defines the item's identity, pick-up behavior, and UI presentation.                                     |
| `SpriteComponent`       | `image_file` (for in-hand)                                                    | Specifies the visual representation when the knife is held by the player.                               |
| `AbilityComponent`      | `throw_as_item`                                                               | Links the item to a throwing ability.                                                                   |

This entity is designed to be a simple, throwable projectile that can be picked up and used by the player. Its `attach_to_surfaces_knife_style` attribute suggests a unique throwing mechanic.