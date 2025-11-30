---
title: Alchemist's Key Entity
category: entities
---

# Alchemist's Key Entity

This document describes the `key.xml` entity, representing the Alchemist's Key in Noita. This item is a unique projectile with physics properties and specific item behaviors.

## Core Components

The Alchemist's Key is defined by several key components that dictate its physical behavior, visual representation, and item functionality.

### Physics Components

These components govern how the key interacts with the game world physically.

*   **`PhysicsBodyComponent`**:
    *   `uid`: `1` (Unique identifier for the physics body)
    *   `is_bullet`: `1` (Indicates it's a projectile)
    *   `auto_clean`: `0` (Prevents automatic removal from the world)
    *   `on_death_leave_physics_body`: `1` (Leaves a physics body upon destruction)
    *   `hax_fix_going_through_ground`: `1` (A fix for potential ground clipping issues)

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/key.png` (The visual sprite for the key in the world)
    *   `material`: `item_box2d_glass` (Defines its physical material properties)

*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed`: `180` (Maximum speed when thrown)
    *   `throw_force_coeff`: `1.5` (Coefficient for throw force calculation)

*   **`VelocityComponent`**:
    *   Manages the key's velocity.

### Item Components

These components define the key's behavior as an inventory item.

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/in_hand/key.png` (Sprite when held in hand)
    *   `offset_x`, `offset_y`: `4`, `6` (Positioning offsets when held)

*   **`ItemComponent`**:
    *   `item_name`: `$item_key` (Internal name, likely localized)
    *   `is_pickable`: `1` (Can be picked up by the player)
    *   `is_equipable_forced`: `1` (Can be equipped directly)
    *   `ui_sprite`: `data/ui_gfx/items/key.png` (Sprite for the UI inventory)
    *   `ui_description`: `$itemdesc_key_0` (Localized description)
    *   `preferred_inventory`: `QUICK` (Default inventory slot)

*   **`AbilityComponent`**:
    *   `ui_name`: `$item_key` (Name displayed in UI)
    *   `throw_as_item`: `1` (Can be thrown as an item)
    *   `gun_config`: `deck_capacity="0"` (No deck capacity, not a spell gun)

*   **`UIInfoComponent`**:
    *   `name`: `$item_key` (Name displayed in UI)

## Scripting and Variables

The key also incorporates scripting for dynamic behavior.

*   **`VariableStorageComponent`**:
    *   `name`: `status`, `value_int`: `0` (Stores an integer status, initialized to 0)
    *   `name`: `music_machine`, `value_int`: `0` (Stores an integer related to a music machine, initialized to 0)

*   **`LuaComponent`**:
    *   `script_source_file`: `data/entities/animals/boss_alchemist/key_music.lua` (External Lua script for custom logic)
    *   `execute_every_n_frame`: `60` (The script executes every 60 frames)

## Tags

The entity is tagged with: `hittable`, `teleportable_NOT`, `item_physics`, `alchemist_key`. These tags define its interaction capabilities and identify it as the Alchemist's Key.