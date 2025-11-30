---
title: Gold Nugget (1000 Value)
category: entities
---

# Gold Nugget (1000 Value)

This document details the configuration for a gold nugget item in Noita, specifically one with a value of 1000. This item is designed to be picked up by the player and contributes to their gold count.

## Core Components

### `UIInfoComponent`
Provides basic information for the item's display in the game world.

*   **`name`**: `$item_goldnugget` - The internal name used for UI elements.

### `PhysicsBodyComponent`
Defines the physical properties of the gold nugget in the game world.

*   **`uid`**: `1` - Unique identifier for this component.
*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when inactive to save resources.
*   **`hax_fix_going_through_ground`**: `1` - A fix to prevent the item from falling through the ground.

### `PhysicsImageShapeComponent`
Defines the visual shape and material of the gold nugget for physics interactions.

*   **`image_file`**: `data/items_gfx/goldnugget_20px.png` - The sprite used for the nugget's visual representation.
*   **`material`**: `gold_box2d` - The physics material applied to the nugget.

### `VariableStorageComponent`
Stores custom variables associated with the entity.

*   **`name`**: `gold_value` - The name of the variable.
*   **`value_int`**: `1000` - The integer value assigned to `gold_value`, representing the nugget's worth.

### `ItemComponent`
Defines the item's behavior and properties when interacting with the player's inventory.

*   **`item_name`**: `$item_goldnugget_1000` - The specific name for this variant of the gold nugget.
*   **`auto_pickup`**: `1` - The item will be automatically picked up by the player when they are near it.
*   **`stats_count_as_item_pick_up`**: `0` - This item does not count towards the player's item pickup statistics.
*   **`is_pickable`**: `1` - The item can be picked up by the player.
*   **`ui_sprite`**: `data/ui_gfx/items/goldnugget.png` - The sprite used for the item in the player's UI.
*   **`preferred_inventory`**: `FULL` - Suggests the item should be placed in the player's main inventory.

### `HitboxComponent`
Defines the collision area of the gold nugget.

*   **`aabb_min_x`**: `-3`, **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-5`, **`aabb_max_y`**: `0`

### `LifetimeComponent`
Determines how long the item will exist before despawning.

*   **`lifetime`**: `900` - The item will last for 900 frames.

## Scripting and Behavior

### `LuaComponent` (Item Pickup)
Handles the logic when the item is picked up by the player.

*   **`script_item_picked_up`**: `data/scripts/items/gold_pickup.lua` - Executes the specified Lua script upon pickup.

### `LuaComponent` (Gold Explosion)
Triggers a visual effect when the item is added to the game.

*   **`script_source_file`**: `data/scripts/perks/gold_explosion.lua` - The script responsible for the gold explosion effect.
*   **`execute_on_added`**: `1` - The script will execute immediately after the entity is added to the game.
*   **`remove_after_executed`**: `1` - The script component will be removed after its execution.

## Visual Effects (Particle Emitters)

The gold nugget features several `SpriteParticleEmitterComponent` instances to create a shimmering, glittery effect. These emitters use different sprite files and have randomized parameters for lifetime, emission rate, scale, and position to create a dynamic visual.

### Emitter 1 (shine\_07.xml)

*   **`sprite_file`**: `data/particles/shine_07.xml`
*   **`lifetime`**: `0.3`
*   **`emission_interval_min_frames`**: `20`
*   **`emission_interval_max_frames`**: `250`
*   **`count_min`**: `1`, **`count_max`**: `1`
*   **Randomization**: Scale, position, and animation speed are randomized within specified ranges.

### Emitter 2 (shine\_08.xml)

*   **`sprite_file`**: `data/particles/shine_08.xml`
*   **`lifetime`**: `0.2`
*   **`randomize_lifetime.min`**: `0.1`, **`randomize_lifetime.max`**: `0.8`
*   **`emission_interval_min_frames`**: `10`
*   **`emission_interval_max_frames`**: `100`
*   **`count_min`**: `1`, **`count_max`**: `1`
*   **Randomization**: Scale, position, and animation speed are randomized.

### Emitter 3 (shine\_06.xml)

*   **`sprite_file`**: `data/particles/shine_06.xml`
*   **`lifetime`**: `0.56`
*   **`emission_interval_min_frames`**: `100`
*   **`emission_interval_max_frames`**: `600`
*   **`count_min`**: `1`, **`count_max`**: `1`
*   **Randomization**: Scale, position, and animation speed are randomized.