---
title: Base Wand Physics Entity
category: entities
---

# Base Wand Physics Entity

This document describes the core components of a base wand entity in Noita, focusing on its physical properties and how it interacts with the game world. This entity serves as a foundational template for various wands.

## Key Components

### `ItemComponent`

This component marks the entity as an item that can be picked up and interacted with in the game world.

*   **`is_pickable`**: `1` - Indicates that the item can be picked up by the player.

### `VelocityComponent`

Defines the basic physics properties related to movement and gravity.

*   **`gravity_y`**: `400` - The strength of gravity applied to the entity along the Y-axis.
*   **`air_friction`**: `0.55` - The amount of friction applied when the entity is in the air.
*   **`terminal_velocity`**: `1000` - The maximum speed the entity can reach due to gravity.

### `HitboxComponent`

Determines the collision boundaries of the entity.

*   **`aabb_max_x`, `aabb_max_y`**: `4`, `4` - Defines the maximum extent of the bounding box.
*   **`aabb_min_x`, `aabb_min_y`**: `-4`, `-4` - Defines the minimum extent of the bounding box.
*   **`is_enemy`, `is_item`, `is_player`**: `0` - These are set to `0`, meaning this hitbox does not represent an enemy, an item for interaction, or the player.

### `SpriteComponent`

Handles the visual representation of the entity.

*   **`image_file`**: `"data/items_gfx/handgun.xml"` - Specifies the graphical asset used for the sprite.
*   **`z_index`**: `-1.5` - Controls the layering of the sprite, placing it behind other elements.

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `64` - The radius of the light emitted by the entity.

### `AudioLoopComponent`

Manages looping sound effects associated with the entity. This entity has two such components, likely for different sound types.

*   **`file`**: `"data/audio/Desktop/projectiles.bank"` - The audio bank containing the sound effects.
*   **`event_name`**: Varies (`"player_projectiles/digger/loop"`, `"player_projectiles/spray/loop"`) - The specific sound event to play.
*   **`volume_autofade_speed`**: `0.1` - Controls how quickly the volume fades out.

### `PhysicsBodyComponent`

Defines the entity as a physics body, enabling it to interact with the physics engine.

*   **`uid`**: `1` - A unique identifier for the physics body.
*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive to save performance.
*   **`is_bullet`**: `1` - Marks this entity as a projectile or bullet.
*   **`auto_clean`**: `0` - Prevents the physics body from being automatically removed.
*   **`hax_fix_going_through_ground`**: `1` - A workaround to prevent the entity from passing through the ground.
*   **`hax_wait_till_pixel_scenes_loaded`**: `1` - Ensures physics updates only after pixel scenes are loaded.

### `PhysicsShapeComponent`

Defines the collision shape of the physics body.

*   **`is_based_on_sprite`**: `1` - The shape is derived from the entity's sprite.
*   **`radius_x`, `radius_y`**: `6`, `2.5` - If not based on sprite, these would define the radii of an ellipse.
*   **`friction`**: `0.35` - The amount of friction applied during collisions.
*   **`restitution`**: `0.15` - The bounciness of the entity during collisions.
*   **`local_position_x`, `local_position_y`**: `3.0`, `0.0` - The offset of the physics shape relative to the entity's origin.