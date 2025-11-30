---
title: Base Torch Entity
category: entities
---

# Base Torch Entity

This document details the `base_torch.xml` entity, which defines the fundamental properties of a torch in Noita. This entity serves as a blueprint for torches that can be found in the game world and potentially wielded by the player.

## Core Components

The `base_torch` entity is constructed using several key components that dictate its behavior and appearance.

### `ItemComponent`

This component marks the entity as an item that can be interacted with in the game world.

*   **`_tags`**: `enabled_in_world` - Indicates the item is active when placed in the game world.

### `TorchComponent`

This component specifically defines the torch functionality.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The torch is active both in the world and when held by the player.

### `VelocityComponent`

Governs the physical movement and momentum of the torch.

*   **`_tags`**: `enabled_in_world`
*   **`gravity_y`**: `400` - The strength of gravity pulling the torch downwards.
*   **`air_friction`**: `0.55` - The resistance to movement in the air.
*   **`terminal_velocity`**: `1000` - The maximum speed the torch can reach due to gravity.

### `SimplePhysicsComponent`

Provides basic physics simulation for the entity.

*   **`_tags`**: `enabled_in_world`

### `HitboxComponent`

Defines the collision boundaries of the torch.

*   **`_tags`**: `enabled_in_world`
*   **`aabb_min_x`**: `-3` - Minimum X-axis boundary for the bounding box.
*   **`aabb_max_x`**: `3` - Maximum X-axis boundary for the bounding box.
*   **`aabb_min_y`**: `-5` - Minimum Y-axis boundary for the bounding box.
*   **`aabb_max_y`**: `0` - Maximum Y-axis boundary for the bounding box.
*   **`is_enemy`**: `0` - Not an enemy.
*   **`is_item`**: `0` - Not a standard item (likely because it's a prop).
*   **`is_player`**: `0` - Not the player.

### `LightComponent`

Manages the light emitted by the torch.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand`
*   **`_enabled`**: `1` - The light is active.
*   **`r`**: `255` - Red color component.
*   **`g`**: `168` - Green color component.
*   **`b`**: `155` - Blue color component.
*   **`radius`**: `64` - The range of the light.
*   **`fade_out_time`**: `0.75` - How long it takes for the light to fade.

### `SpriteComponent` (Multiple)

These components define the visual appearance of the torch using sprite sheets.

#### Main Sprite

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand`, `character`
*   **`image_file`**: `data/items_gfx/torch.xml` - Path to the main sprite sheet.
*   **`next_rect_animation`**: `default`
*   **`rect_animation`**: `default`

#### Emissive Center Sprite

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand`, `character`
*   **`image_file`**: `data/items_gfx/torch_emissive_center.xml` - Path to the emissive center sprite sheet.
*   **`offset_x`**: `0`
*   **`offset_y`**: `0`
*   **`emissive`**: `1` - This sprite contributes to the light emission.
*   **`additive`**: `0`
*   **`smooth_filtering`**: `0`

#### Emissive Sprite

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand`, `character`
*   **`image_file`**: `data/items_gfx/torch_emissive.xml` - Path to the emissive sprite sheet.
*   **`offset_x`**: `0`
*   **`offset_y`**: `0`
*   **`emissive`**: `1` - This sprite contributes to the light emission.
*   **`additive`**: `1` - Uses additive blending for light effects.
*   **`smooth_filtering`**: `1`

### `SpriteAnimatorComponent`

Handles the animation of the torch's sprites.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand`

## Entity Tags

The `base_torch` entity has the following tags:

*   `drillable`: Can be destroyed by drills.
*   `kickable`: Can be kicked.
*   `teleportable_NOT`: Cannot be teleported.
*   `prop`: Acts as a static or interactive object in the environment.
*   `torch`: Identifies this entity as a torch.