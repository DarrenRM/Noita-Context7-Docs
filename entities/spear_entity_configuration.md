---
title: Spear Entity Configuration
category: entities
---

# Spear Entity Configuration

This document details the configuration of the `spear.xml` entity, focusing on its physical properties, projectile behavior, and item characteristics for use in Noita modding.

## Core Components

The spear entity is defined by several key components that dictate its behavior and appearance.

### Physics Components

These components define the spear's physical presence and interaction with the game world.

*   **`PhysicsBodyComponent`**:
    *   `uid`: Unique identifier for the physics body.
    *   `allow_sleep`: Allows the body to enter a sleep state when inactive to save performance.
    *   `is_bullet`: Marks this as a projectile that can pass through other entities.
    *   `on_death_leave_physics_body`: Ensures the physics body persists even if the entity is destroyed.
    *   `send_collision_messages`: Enables collision event notifications.

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual sprite for the spear's physical form (`data/items_gfx/spear.png`).
    *   `material`: Defines the physical material properties (`rock_box2d`).

*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed`: The maximum speed the spear can be thrown.
    *   `throw_force_coeff`: Coefficient influencing the force applied when throwing.
    *   `tip_check_offset_min`/`max`: Defines the range for checking if the spear tip is near a surface for attachment.
    *   `attach_to_surfaces_knife_style`: Enables attachment behavior similar to knives.

*   **`ProjectileComponent`**:
    *   `lifetime`: How long the projectile exists before despawning (-1 means infinite).
    *   `penetrate_entities`: Allows the projectile to pass through multiple entities.

*   **`VelocityComponent`**:
    *   This component is present but has no specific attributes defined, implying it takes default velocity values.

### Item Components

These components define the spear as an equippable and usable item within the game.

*   **`SpriteComponent`**:
    *   `_enabled="0"`: This sprite is disabled by default, likely because the `PhysicsImageShapeComponent` handles the visual representation during flight.
    *   `offset_x`/`offset_y`: Adjusts the sprite's position when held.
    *   `image_file`: The sprite used when the item is in hand (`data/items_gfx/spear.png`).

*   **`ItemComponent`**:
    *   `item_name`: The display name of the item ("Heavy Spear").
    *   `is_pickable`: Allows the player to pick up the spear.
    *   `is_equipable_forced`: The spear is designed to be equipped.
    *   `ui_sprite`: The icon displayed in the UI (`data/ui_gfx/items/knife.png`).
    *   `ui_description`: Text displayed in the UI ("Equip and throw.").
    *   `preferred_inventory`: Suggests the preferred inventory slot ("QUICK").

*   **`AbilityComponent`**:
    *   `ui_name`: The name displayed for the ability associated with this item ("Heavy Spear").
    *   `throw_as_item`: Indicates that this item is thrown.
    *   `gun_config`: Contains settings for projectile firing, with `deck_capacity="0"` suggesting it doesn't draw from a wand deck.

*   **`UIInfoComponent`**:
    *   `name`: The internal name used for UI purposes ("Throwing knife").

## Key Attributes Summary

| Component Type           | Key Attribute(s)                                                              | Description