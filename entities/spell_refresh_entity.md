---
title: Spell Refresh Entity
category: entities
---

# Spell Refresh Entity

This document describes the `spell_refresh.xml` entity, which represents a spell refresh item in Noita. This entity is designed to be picked up by the player and provides a specific gameplay effect.

## Core Components

The `spell_refresh.xml` entity is composed of several key components that define its behavior and appearance:

### `VelocityComponent`
- **Purpose:** Manages the entity's velocity.
- **Attributes:** None explicitly defined in this snippet, implying default physics behavior.

### `SimplePhysicsComponent`
- **Purpose:** Enables basic physics interactions for the entity.

### `UIInfoComponent`
- **Purpose:** Provides information displayed in the user interface.
- **Key Attribute:**
    - `name`: `$item_spell_refresh` - This is a localization key for the item's name.

### `HitboxComponent`
- **Purpose:** Defines the collision area of the entity.
- **Key Attributes:**
    - `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the bounding box dimensions.
    - `is_item`: Set to `1`, indicating this is an item.
    - `is_player`, `is_enemy`: Set to `0`, meaning it's neither a player nor an enemy.

### `ItemComponent`
- **Purpose:** Configures the entity as an item that can be interacted with.
- **Key Attributes:**
    - `item_name`: `$item_spell_refresh` - Links to the UI name.
    - `auto_pickup`: Set to `1`, meaning the item will be automatically picked up by the player when close enough.
    - `stats_count_as_item_pick_up`: Set to `0`, meaning picking this up does not count towards certain game statistics.
    - `play_spinning_animation`, `play_pick_sound`: Set to `0`, disabling these default item behaviors.

### `LuaComponent`
- **Purpose:** Executes custom Lua scripting for the entity.
- **Key Attribute:**
    - `script_item_picked_up`: `data/scripts/items/spell_refresh.lua` - This specifies the Lua script that runs when the item is picked up. This script likely contains the logic for what "spell refresh" actually does in-game.

### `LightComponent`
- **Purpose:** Adds a light source to the entity.
- **Key Attributes:**
    - `r`, `g`, `b`: Define the color of the light (white in this case).
    - `radius`: `64` - The range of the light.
    - `fade_out_time`: `0.75` - How long the light takes to fade.

### `SpriteComponent`
- **Purpose:** Defines the visual representation of the entity.
- **Key Attributes:**
    - `image_file`: `data/items_gfx/spell_refresh.xml` - Points to the graphical asset for the item.
    - `offset_x`, `offset_y`: Adjust the sprite's position relative to the entity's origin.
    - `z_index`: `20` - Controls the rendering order of the sprite.

## Summary

The `spell_refresh.xml` entity is a simple item designed for automatic pickup. Its primary function is determined by the `data/scripts/items/spell_refresh.lua` script, which is executed upon pickup. The entity also features a white light emission and a distinct sprite for visual feedback.