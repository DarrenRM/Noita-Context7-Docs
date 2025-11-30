---
title: Orb Base Entity Definition
category: entities
---

# Orb Base Entity Definition

This document describes the base entity definition for orbs in Noita, serving as a template for various orb types. It outlines the fundamental components and behaviors common to all orbs.

## Core Components

The `orb_base.xml` file defines a foundational entity with several key components that dictate its behavior and appearance.

### `Entity`

The root element for the orb entity.

*   **`tags`**: `hittable`, `teleportable_NOT`, `polymorphable_NOT` - Defines basic interaction properties.

### `VelocityComponent`

Handles the entity's velocity and movement. This is typically an empty component for orbs, implying their movement is managed by other systems or scripts.

### `SimplePhysicsComponent`

Provides basic physics simulation for the entity. Similar to `VelocityComponent`, this is often a placeholder for orbs.

### `HitboxComponent`

Defines the physical boundaries of the orb for collision detection.

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Define the axis-aligned bounding box.
*   **`is_enemy="0"`**: Indicates the orb is not an enemy.
*   **`is_item="1"`**: Marks the entity as an item.
*   **`is_player="0"`**: Indicates the entity is not the player.

### `UIInfoComponent`

Provides information displayed in the user interface.

*   **`name="$item_orb"`**: The internal name identifier for the orb, often localized.

### `ItemComponent`

Defines properties related to the orb as an item.

*   **`item_name="$item_orb"`**: The internal item name.
*   **`play_spinning_animation="0"`**: Disables a default spinning animation.
*   **`auto_pickup="0"`**: The orb does not automatically get picked up.
*   **`play_pick_sound="0"`**: Disables a default pickup sound.
*   **`enable_orb_hacks="1"`**: Enables specific orb-related functionalities.

### `CameraBoundComponent`

Controls how the entity interacts with the camera's view.

*   **`max_count="20"`**: Limits the number of these entities that can be active within the camera's view.
*   **`distance="160000"`**: The maximum distance from the camera at which the entity can exist.

### `OrbComponent`

A specific component for orb entities.

*   **`orb_id="0"`**: A unique identifier for this specific orb type.

### `LightComponent`

Adds a light source to the orb.

*   **`r`, `g`, `b`**: RGB color values for the light.
*   **`radius`**: The radius of the light's influence.
*   **`fade_out_time`**: How long the light takes to fade out.

### `SpriteComponent`

Defines the visual representation of the orb. Multiple `SpriteComponent` instances are used to handle different states of the orb (undiscovered, discovered, picked up).

*   **`_tags`**: `enabled_in_world`, and state-specific tags like `orb_undiscovered`, `orb_discovered`, `orb_picked`.
*   **`image_file`**: Path to the sprite's image file.
*   **`offset_x`, `offset_y`**: Adjusts the sprite's position relative to the entity's origin.
*   **`z_index`**: Determines the rendering order of the sprite.

### `AudioLoopComponent`

Manages looping audio for the orb.

*   **`auto_play="1"`**: The audio starts automatically.
*   **`file`**: Path to the audio bank.
*   **`event_name`**: The name of the audio event to play.

### `VariableStorageComponent`

Allows storing custom variables within the entity.

*   **`name="card_name"`**: The name of the variable.
*   **`value_string="LIGHT_BULLET"`**: The string value assigned to the variable.

### `LuaComponent`

Integrates Lua scripts to add custom logic.

*   **`script_source_file`**: Path to the Lua script executed when the entity is added.
*   **`script_item_picked_up`**: Path to the Lua script executed when the item is picked up.

## Cosmetic Tags and States

The `SpriteComponent`s utilize specific tags to control their visibility based on the orb's discovery state:

*   **`orb_undiscovered`**: The sprite is enabled when the orb has not been found in any previous runs.
*   **`orb_discovered`**: The sprite is enabled when the orb has been found in a previous run but not yet in the current one.
*   **`orb_picked`**: The sprite is enabled when the orb has been found and picked up during the current run.

## Scripting Integration

The orb's behavior is extended through Lua scripts:

*   **`data/scripts/items/orb_init.lua`**: This script is executed once when the orb entity is initialized, likely for setup and initial configuration.
*   **`data/scripts/items/orb_pickup.lua`**: This script handles the logic that occurs when the player picks up the orb.