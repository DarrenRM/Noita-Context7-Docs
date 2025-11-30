---
title: Gold Nugget (200 Value)
category: entities
---

# Gold Nugget (200 Value)

This document details the configuration for a gold nugget item in Noita, specifically one with a value of 200.

## Core Components

### `UIInfoComponent`
This component defines the in-game UI information for the gold nugget.
- `name`: `$item_goldnugget` - The internal name used for UI display.

### `PhysicsBodyComponent`
Defines the physical properties of the gold nugget in the game world.
- `uid`: `1` - Unique identifier for the physics body.
- `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive.
- `linear_damping`: `0` - No linear damping applied.
- `angular_damping`: `0` - No angular damping applied.
- `fixed_rotation`: `0` - Allows rotation.
- `hax_fix_going_through_ground`: `1` - A fix to prevent the item from falling through the ground.

### `PhysicsImageShapeComponent`
Defines the visual shape and material of the gold nugget based on an image.
- `body_id`: `1` - Links this shape to the `PhysicsBodyComponent` with UID 1.
- `image_file`: `data/items_gfx/goldnugget_12px.png` - The sprite used for the nugget's visual representation.
- `material`: `gold_box2d` - The physics material applied.

### `VariableStorageComponent`
Stores custom variables associated with the entity.
- `name`: `gold_value` - The name of the variable.
- `value_int`: `200` - The integer value assigned to `gold_value`, representing the nugget's worth.

### `ItemComponent`
Defines the item-specific properties and behaviors.
- `auto_pickup`: `1` - The item will be automatically picked up by the player.
- `item_name`: `$item_goldnugget_200` - The internal name for this specific gold nugget variant.
- `stats_count_as_item_pick_up`: `0` - Picking this up does not count towards general item pickup statistics.
- `is_pickable`: `1` - The item can be picked up.
- `ui_sprite`: `data/ui_gfx/items/goldnugget.png` - The sprite used in the UI inventory.
- `play_pick_sound`: `0` - No specific sound plays when picked up.
- `preferred_inventory`: `FULL` - Suggests it should be placed in the main inventory.

### `HitboxComponent`
Defines the collision area of the gold nugget.
- `aabb_min_x`: `-3`
- `aabb_max_x`: `3`
- `aabb_min_y`: `-5`
- `aabb_max_y`: `0`

### `LifetimeComponent`
Determines how long the item persists in the world.
- `lifetime`: `900` - The item will disappear after 900 frames (approximately 15 seconds).

## Scripting and Behavior

### `LuaComponent` (Item Pickup)
- `script_item_picked_up`: `data/scripts/items/gold_pickup.lua` - This script is executed when the item is picked up, likely handling the addition of gold value to the player.

### `LuaComponent` (Gold Explosion)
- `script_source_file`: `data/scripts/perks/gold_explosion.lua` - This script is executed immediately upon the entity being added to the world. It's likely responsible for the visual "explosion" or effect when the gold nugget spawns.
- `execute_on_added`: `1` - Ensures the script runs when the entity is created.
- `remove_after_executed`: `1` - The script component is removed after execution.

## Visual Effects (Particle Emitters)

The gold nugget features two `SpriteParticleEmitterComponent` instances to create a shimmering, glittery effect.

### Particle Emitter 1
- `sprite_file`: `data/particles/shine_07.xml` - Uses a specific shine particle sprite.
- `lifetime`: `0.3` - Duration of each particle.
- `emission_interval_min_frames`: `50`
- `emission_interval_max_frames`: `500`
- `count_min`: `1`
- `count_max`: `1`
- `additive`: `1` - Particles are added to the scene color.
- `emissive`: `0` - Particles do not emit light.
- `scale`: `1.0`
- `sprite_random_rotation`: `1` - Particles can have random rotations.
- `randomize_scale`: `+/- 0.1`
- `randomize_position`: `+/- 6` on X and Y axes.
- `randomize_animation_speed_coeff`: `0.667` to `1.0`

### Particle Emitter 2
- `sprite_file`: `data/particles/shine_08.xml` - Uses a different shine particle sprite.
- `lifetime`: `0.2`
- `randomize_lifetime`: `0.1` to `0.8`
- `emission_interval_min_frames`: `40`
- `emission_interval_max_frames`: `150`
- `count_min`: `1`
- `count_max`: `1`
- `additive`: `1`
- `emissive`: `0`
- `scale`: `1.0`
- `sprite_random_rotation`: `1`
- `randomize_scale`: `+/- 0.1`
- `randomize_position`: `+/- 5` on X and Y axes.
- `randomize_animation_speed_coeff`: `0.667` to `1.0`