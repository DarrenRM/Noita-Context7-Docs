---
title: Test Bullet Entity
category: entities
---

# Test Bullet Entity

This document describes the `test_bullet.xml` entity, which represents a basic bullet projectile in Noita. It's designed for testing and demonstrates fundamental components for projectile behavior.

## Key Components and Attributes

This entity utilizes several core Noita components to define its appearance, physics, and interaction properties.

### Entity Attributes

*   **name**: The internal name of the entity.
*   **serialize**: Determines if the entity should be saved with the game state.
*   **tags**: General tags applied to the entity. `hittable` indicates it can be interacted with.

### `_Transform`

Defines the initial position and rotation of the entity in the game world.

*   **position.x**: X-coordinate of the entity's spawn point.
*   **position.y**: Y-coordinate of the entity's spawn point.
*   **rotation**: Initial rotation in degrees.

### `HitboxComponent`

Defines the collision area of the entity.

*   **aabb_max_x/y**: Maximum bounds of the Axis-Aligned Bounding Box.
*   **aabb_min_x/y**: Minimum bounds of the Axis-Aligned Bounding Box.
*   **damage_multiplier**: How much damage this entity deals or takes.
*   **is_enemy**: Whether this entity is considered an enemy.
*   **is_item**: Whether this entity is considered an item.
*   **is_player**: Whether this entity is considered the player.

### `ItemActionComponent`

Links the entity to a specific action ID, often used for weapon effects or spell behaviors.

*   **action_id**: The identifier for the action this item performs (e.g., `HEAVY_BULLET`).

### `ItemComponent`

Defines properties related to the entity being an "item" that can be picked up or interacted with.

*   **camera_max_distance**: Maximum distance the camera can be from the item to be considered.
*   **collect_nondefault_actions**: Whether to collect non-default actions when picked up.
*   **inventory_slot.x/y**: Default inventory slot if picked up.
*   **is_pickable**: Whether the item can be picked up by the player.
*   **is_stackable**: Whether multiple instances of this item can stack in an inventory.
*   **item_name**: The internal name of the item.
*   **ui_description**: The description shown in the UI.
*   **ui_sprite**: The sprite used for the item in the UI.

### `SimplePhysicsComponent`

Enables basic physics simulation for the entity.

*   **can_go_up**: Whether the entity can move upwards.

### `SpriteComponent`

Defines the visual representation of the entity. This entity has two `SpriteComponent`s: one for when the item is identified and one for when it's unidentified.

#### Identified Sprite (`item_identified` tag)

*   **image_file**: Path to the sprite image (`data/ui_gfx/gun_actions/light_bullet.png`).
*   **offset_x/y**: Offset of the sprite from the entity's origin.
*   **z_index**: Determines the rendering order.

#### Unidentified Sprite (`item_unidentified` tag)

*   **image_file**: Path to the sprite image for unidentified items (`data/ui_gfx/gun_actions/unidentified.png`).

### `VelocityComponent`

Defines the movement properties of the entity.

*   **air_friction**: Friction applied when in the air.
*   **gravity_x/y**: The gravitational force applied to the entity.
*   **terminal_velocity**: The maximum speed the entity can reach due to gravity.