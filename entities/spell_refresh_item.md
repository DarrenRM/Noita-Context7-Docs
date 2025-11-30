---
title: Spell Refresh Item
category: entities
---

# Spell Refresh Item

This document describes the `spell_refresh.xml` entity, which represents the Spell Refresh item pickup in Noita. This item, when picked up, provides a unique benefit to the player.

## Core Functionality

The primary purpose of the Spell Refresh item is to grant the player a spell refresh. This is handled by the `LuaComponent`.

### LuaComponent

*   **`script_item_picked_up`**: Specifies the Lua script that executes when the item is picked up.
    *   `data/scripts/items/spell_refresh.lua`: This script contains the logic for what happens when the player collects the Spell Refresh.

## Visual and Physical Properties

This section details how the item appears and interacts physically in the game world.

### SpriteComponent

Defines the visual representation of the Spell Refresh item.

*   **`image_file`**: Points to the graphical asset for the item.
    *   `data/items_gfx/spell_refresh.xml`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `9`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `18`
*   **`z_index`**: Determines the rendering order.
    *   `20`

### LightComponent

Adds a light source to the item, making it visually distinct.

*   **`r`, `g`, `b`**: Color components of the light (white in this case).
    *   `255`, `255`, `255`
*   **`radius`**: The range of the light.
    *   `64`
*   **`fade_out_time`**: How long the light takes to fade.
    *   `0.75`

### HitboxComponent

Defines the collision area of the item.

*   **`aabb_min_x`, `aabb_max_x`**: Defines the horizontal bounds of the hitbox.
    *   `-6`, `6`
*   **`aabb_min_y`, `aabb_max_y`**: Defines the vertical bounds of the hitbox.
    *   `-8`, `0`
*   **`is_item`**: Indicates this hitbox belongs to an item.
    *   `1`

### SimplePhysicsComponent

Enables basic physics for the item, allowing it to fall and interact with the environment.

### VelocityComponent

Initializes the velocity properties for the item.

## Item Pickup Behavior

This section covers how the item behaves as a pickup in the game.

### ItemComponent

Configures the item's properties as a collectible.

*   **`item_name`**: The internal name of the item, used for localization.
    *   `$item_spell_refresh`
*   **`auto_pickup`**: If set to `1`, the item will be automatically picked up by the player when they are close enough.
    *   `1`
*   **`stats_count_as_item_pick_up`**: Determines if picking up this item contributes to player statistics.
    *   `0` (This item does not count towards general item pickups for stats).

## Entity Tags

The `tags` attribute provides metadata about the entity, influencing its behavior and interactions.

*   **`drillable`**: The item can be destroyed by drilling.
*   **`hittable`**: The item can be hit by projectiles or other attacks.
*   **`teleportable_NOT`**: This item cannot be teleported.
*   **`item_pickup`**: Marks this entity as an item that can be picked up.