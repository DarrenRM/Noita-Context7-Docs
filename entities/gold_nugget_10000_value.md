---
title: Gold Nugget (10000 Value)
category: entities
---

# Gold Nugget (10000 Value)

This document details the configuration of a large gold nugget item in Noita, specifically one with a value of 10000. This item is designed to be a significant source of in-game currency.

## Core Components

### `Entity`
The root element defining the gold nugget.

*   **`name`**: `unknown` (This is a placeholder and can be customized).
*   **`tags`**: `item_physics`, `gold_nugget` (Essential for physics and identification).

### `UIInfoComponent`
Provides information for the user interface.

*   **`_tags`**: `enabled_in_world`
*   **`name`**: `$item_goldnugget` (Refers to a localized string for the item's name).

### `PhysicsBodyComponent`
Defines the physical properties of the gold nugget.

*   **`uid`**: `1`
*   **`allow_sleep`**: `1` (Allows the physics body to sleep when inactive).
*   **`hax_fix_going_through_ground`**: `1` (A specific fix for physics issues).
*   **`on_death_leave_physics_body`**: `1` (Ensures physics properties persist).

### `PhysicsImageShapeComponent`
Defines the visual shape and material of the gold nugget.

*   **`body_id`**: `1` (Links to the `PhysicsBodyComponent`).
*   **`centered`**: `1` (The image is centered on the physics body).
*   **`image_file`**: `data/items_gfx/easter/golden_idol.png` (The sprite used for the nugget).
*   **`material`**: `metal_prop` (Determines interaction with other physics objects).

### `VariableStorageComponent`
Stores custom variables associated with the entity.

*   **`name`**: `gold_value`
*   **`value_int`**: `10000` (This is the key attribute defining the nugget's worth).

### `ItemComponent`
Defines the item's behavior and properties when picked up.

*   **`_tags`**: `enabled_in_world`
*   **`auto_pickup`**: `1` (The item will be automatically picked up by the player).
*   **`item_name`**: `$item_goldnugget_10000` (Localized name for the item).
*   **`stats_count_as_item_pick_up`**: `0` (Does not count towards item pickup statistics).
*   **`is_pickable`**: `1` (The item can be picked up).
*   **`ui_sprite`**: `data/ui_gfx/items/goldnugget.png` (The sprite shown in the inventory).
*   **`preferred_inventory`**: `FULL` (Suggests it should go into the main inventory).

### `HitboxComponent`
Defines the collision area of the item.

*   **`aabb_min_x`**: `-3`
*   **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-5`
*   **`aabb_max_y`**: `0`

### `LifetimeComponent`
Sets a lifespan for the item.

*   **`lifetime`**: `900` (The item will disappear after 900 frames).

### `LuaComponent` (Scripting)

*   **`script_item_picked_up`**: `data/scripts/items/gold_pickup.lua` (Handles logic when the item is picked up).
*   **`script_source_file`**: `data/scripts/perks/gold_explosion.lua` (Executes a script upon entity creation, likely for effects).
    *   **`execute_on_added`**: `1`
    *   **`remove_after_executed`**: `1`

## Visual Effects (Particle Emitters)

The following `SpriteParticleEmitterComponent` elements create visual flair, simulating a shimmering or glittering effect.

### `SpriteParticleEmitterComponent` (Shine 07)

*   **`sprite_file`**: `data/particles/shine_07.xml`
*   **`lifetime`**: `0.3`
*   **`emission_interval_min_frames`**: `20`
*   **`emission_interval_max_frames`**: `250`
*   **`count_min`**: `1`
*   **`count_max`**: `1`
*   **`additive`**: `1`
*   **`randomize_position`**: Various ranges for X and Y, creating a spread.

### `SpriteParticleEmitterComponent` (Shine 08)

*   **`sprite_file`**: `data/particles/shine_08.xml`
*   **`lifetime`**: `0.2`
*   **`randomize_lifetime`**: `min="0.1"`, `max="0.8"`
*   **`emission_interval_min_frames`**: `20`
*   **`emission_interval_max_frames`**: `150`
*   **`count_min`**: `1`
*   **`count_max`**: `1`
*   **`additive`**: `1`
*   **`randomize_position`**: Various ranges for X and Y.

### `SpriteParticleEmitterComponent` (Shine 06)

*   **`sprite_file`**: `data/particles/shine_06.xml`
*   **`lifetime`**: `0.56`
*   **`emission_interval_min_frames`**: `100`
*   **`emission_interval_max_frames`**: `600`
*   **`count_min`**: `1`
*   **`count_max`**: `1`
*   **`additive`**: `1`
*   **`randomize_position`**: Various ranges for X and Y.