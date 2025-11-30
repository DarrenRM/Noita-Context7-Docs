---
title: Base Item Entity
category: entities
---

# Base Item Entity

This document describes the fundamental structure of an item entity in Noita, as defined in `base_item.xml`. This serves as a foundational template for many in-game items.

## Key Components and Attributes

The `base_item.xml` entity utilizes several core components to define its behavior and appearance.

### `ItemComponent`

This component marks the entity as an item and defines its pickability.

*   **`is_pickable`**: `1` (Boolean) - Indicates that the item can be picked up by the player.

### `VelocityComponent`

Governs the item's movement in the game world.

*   **`gravity_y`**: `400` (Float) - The strength of gravity applied to the item.
*   **`air_friction`**: `0.55` (Float) - The resistance to movement in the air.
*   **`terminal_velocity`**: `1000` (Float) - The maximum speed the item can reach due to gravity.

### `SimplePhysicsComponent`

Provides basic physics interactions for the item.

### `HitboxComponent`

Defines the collision boundaries of the item.

*   **`aabb_max_x`**, **`aabb_max_y`**: `4` (Float) - The maximum X and Y coordinates of the Axis-Aligned Bounding Box (AABB).
*   **`aabb_min_x`**, **`aabb_min_y`**: `-4` (Float) - The minimum X and Y coordinates of the AABB.
*   **`is_enemy`**, **`is_item`**, **`is_player`**: `0` (Boolean) - These are set to `0` to indicate this is not a hostile entity, not a generic item hitbox (but rather a specific item), and not the player.

### `SpriteComponent`

Determines the visual representation of the item.

*   **`image_file`**: `"data/items_gfx/handgun.xml"` (String) - Path to the sprite definition file.
*   **`rect_animation`**, **`next_rect_animation`**: `"default"` (String) - Specifies the default animation states.
*   **`z_index`**: `-1.5` (Float) - Controls the rendering order, placing it slightly behind the player's hand.

### `LightComponent`

Adds a light source originating from the item.

*   **`radius`**: `64` (Float) - The range of the light emitted.

### `AudioLoopComponent`

Manages looping sound effects for the item, particularly when held.

*   **`file`**: `"data/audio/Desktop/projectiles.bank"` (String) - Path to the audio bank.
*   **`event_name`**: `"player_projectiles/digger/loop"` or `"player_projectiles/spray/loop"` (String) - The specific audio event to trigger.
*   **`volume_autofade_speed`**: `0.1` (Float) - Controls how quickly the sound fades in or out.

## Tags

The entity uses various tags to define its behavior and interactions:

*   **`teleportable_NOT`**: Prevents the item from being teleported.
*   **`item`**: Identifies the entity as an item.
*   **`enabled_in_world`**: The component is active when the item is in the game world.
*   **`enabled_in_hand`**: The component is active when the item is held by the player.
*   **`sound_digger`**, **`sound_spray`**: Specific tags for different audio loop behaviors.