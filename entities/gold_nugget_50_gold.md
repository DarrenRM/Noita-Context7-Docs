---
title: Gold Nugget (50 Gold)
category: entities
---

# Gold Nugget (50 Gold)

This document details the configuration for a Gold Nugget item in Noita, specifically one that grants 50 gold.

## Core Components

This section highlights the essential components that define the Gold Nugget's behavior and appearance.

### `UIInfoComponent`

Defines the in-game UI information for the item.

*   **`name`**: `$item_goldnugget` - The internal name used for UI display.

### `PhysicsBodyComponent`

Manages the physical properties of the gold nugget in the game world.

*   **`uid`**: `1` - Unique identifier for this component.
*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when inactive.
*   **`hax_fix_going_through_ground`**: `1` - A workaround to prevent the item from falling through the ground.

### `PhysicsImageShapeComponent`

Defines the visual shape and collision properties based on an image.

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`image_file`**: `data/items_gfx/goldnugget_9px.png` - The sprite used for the nugget's physical representation.
*   **`material`**: `gold_box2d` - The physics material applied, influencing interactions.

### `VariableStorageComponent`

Stores custom variables associated with the entity.

*   **`name`**: `gold_value` - The name of the variable.
*   **`value_int`**: `50` - The integer value stored, representing the gold amount.

### `ItemComponent`

Defines the item's properties as a collectible in the game.

*   **`item_name`**: `$item_goldnugget_50` - The specific name for this variant of the gold nugget.
*   **`auto_pickup`**: `1` - The item will be automatically picked up by the player.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards the player's item pickup statistics.
*   **`is_pickable`**: `1` - The item can be picked up by the player.
*   **`ui_sprite`**: `data/ui_gfx/items/goldnugget.png` - The sprite used in the UI inventory.
*   **`preferred_inventory`**: `FULL` - Indicates where this item is best stored in the inventory.

### `HitboxComponent`

Defines the bounding box for player interaction and collision.

*   **`aabb_min_x`**: `-3`
*   **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-5`
*   **`aabb_max_y`**: `0`

### `LifetimeComponent`

Determines how long the item persists in the game world.

*   **`lifetime`**: `900` - The item will disappear after 900 frames.

## Scripting and Effects

This section details the scripts and particle effects associated with the gold nugget.

### `LuaComponent` (Item Pickup)

Handles the logic when the item is picked up.

*   **`script_item_picked_up`**: `data/scripts/items/gold_pickup.lua` - The script executed when the item is collected.

### `LuaComponent` (Gold Explosion)

Triggers an effect upon the item's creation or addition.

*   **`script_source_file`**: `data/scripts/perks/gold_explosion.lua` - The script responsible for a potential gold explosion effect.
*   **`execute_on_added`**: `1` - The script runs immediately when the entity is added.
*   **`remove_after_executed`**: `1` - The script component is removed after execution.

### `SpriteParticleEmitterComponent` (Shine 1)

Emits particles to create a shimmering effect.

*   **`sprite_file`**: `data/particles/shine_07.xml` - The particle sprite definition.
*   **`lifetime`**: `0.3` - Duration of each emitted particle.
*   **`emission_interval_min_frames`**: `100`
*   **`emission_interval_max_frames`**: `500`
*   **`count_min`**: `1`
*   **`count_max`**: `1`
*   **`additive`**: `1` - Particles are added to the scene color.
*   **`randomize_position`**: Various settings to spread particles around the nugget.

### `SpriteParticleEmitterComponent` (Shine 2)

Another particle emitter for a secondary shimmering effect.

*   **`sprite_file`**: `data/particles/shine_08.xml` - The particle sprite definition.
*   **`lifetime`**: `0.2`
*   **`randomize_lifetime`**: `min="0.1"`, `max="0.8"`
*   **`emission_interval_min_frames`**: `50`
*   **`emission_interval_max_frames`**: `200`
*   **`count_min`**: `1`
*   **`count_max`**: `1`
*   **`additive`**: `1`
*   **`randomize_position`**: Various settings to spread particles around the nugget.