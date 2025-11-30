---
title: Gold Nugget Pickup Entity
category: entities
---

# Gold Nugget Pickup Entity

This document describes the `goldnugget_x.xml` entity, which represents a gold nugget pickup in Noita. This entity is designed to be collected by the player, providing them with gold.

## Key Components and Attributes

The `goldnugget_x.xml` entity is composed of several components that define its behavior and appearance.

### `UIInfoComponent`

This component provides basic information for the UI.

*   **`name`**: `$reward_gold_statue` - This likely refers to a localized string for the item's name in the UI.

### `PhysicsBodyComponent`

Defines the physical properties of the gold nugget.

*   **`uid`**: `1` - A unique identifier for this physics body.
*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when not in motion to save resources.
*   **`linear_damping`**: `0` - No linear damping applied.
*   **`auto_clean`**: `0` - The physics body will not be automatically cleaned up.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent the object from falling through the ground.

### `PhysicsImageShapeComponent`

Defines the visual shape and material of the gold nugget.

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`centered`**: `1` - The image is centered on the physics body.
*   **`image_file`**: `data/entities/animals/boss_centipede/rewards/gold_reward_sprite.png` - The sprite used for the gold nugget.
*   **`material`**: `gold_box2d` - The physics material applied, influencing interactions.

### `VariableStorageComponent`

Stores custom variables associated with the entity.

*   **`name`**: `gold_value` - The name of the variable.
*   **`value_int`**: `200` - The integer value stored, representing the gold amount this nugget provides.

### `ItemComponent`

Defines the item-specific properties and behaviors.

*   **`auto_pickup`**: `1` - The item will be automatically picked up by the player when they are near it.
*   **`item_name`**: `$reward_gold_statue` - The localized name of the item.
*   **`stats_count_as_item_pick_up`**: `0` - This pickup does not count towards the player's item pickup statistics.
*   **`is_pickable`**: `1` - The item can be picked up.
*   **`ui_sprite`**: `data/ui_gfx/items/goldnugget.png` - The sprite used in the player's inventory UI.
*   **`preferred_inventory`**: `FULL` - Indicates where the item should ideally be placed in the inventory.

### `HitboxComponent`

Defines the collision area of the item.

*   **`aabb_min_x`**: `-3`
*   **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-5`
*   **`aabb_max_y`**: `0` - These values define a bounding box for collision detection.

### `LifetimeComponent`

Determines how long the entity exists before despawning.

*   **`lifetime`**: `900` - The entity will exist for 900 game frames.

### `LuaComponent` (for pickup logic)

*   **`script_item_picked_up`**: `data/scripts/items/gold_pickup.lua` - This script is executed when the item is picked up, handling the logic for adding gold to the player.

### `LuaComponent` (for gold explosion)

*   **`script_source_file`**: `data/scripts/perks/gold_explosion.lua` - This script is executed immediately upon the entity being added to the world.
*   **`execute_on_added`**: `1` - Ensures the script runs when the entity spawns.
*   **`remove_after_executed`**: `1` - The script component is removed after execution. This suggests a one-time effect upon spawning, possibly related to a visual effect or a small gold burst.

### `SpriteParticleEmitterComponent` (x2)

These components are responsible for generating particle effects, specifically a shimmering or glittering effect.

*   **`sprite_file`**: Specifies the particle sprite (e.g., `data/particles/shine_07.xml`).
*   **`lifetime`**: Duration of individual particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing of particle emissions.
*   **`count_min` / `count_max`**: Number of particles emitted per burst.
*   **`additive`**: `1` - Particles are added to the scene, creating a brighter effect.
*   **`scale`**: Base scale of the particles.
*   **`randomize_scale`**: Adds variation to particle size.
*   **`randomize_position`**: Adds variation to particle spawn location.
*   **`randomize_animation_speed_coeff`**: Adds variation to particle animation speed.

These two emitters likely create a subtle, continuous sparkle effect around the gold nugget.