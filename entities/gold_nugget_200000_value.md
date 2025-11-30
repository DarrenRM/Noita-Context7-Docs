---
title: Gold Nugget (200000 Value)
category: entities
---

# Gold Nugget (200000 Value)

This entity represents a large gold nugget, providing a significant amount of gold value when picked up.

## Key Components

### `UIInfoComponent`
- **name**: `$item_goldnugget` - The internal name used for UI elements.

### `PhysicsBodyComponent`
- Manages the physical properties of the gold nugget in the game world.
- `allow_sleep`: `1` - Allows the physics body to sleep when inactive.
- `fixed_rotation`: `0` - Allows rotation.
- `hax_fix_going_through_ground`: `1` - A fix to prevent it from falling through the ground.

### `PhysicsImageShapeComponent`
- Defines the visual representation and collision shape.
- `image_file`: `data/items_gfx/easter/golden_idol_big.png` - The sprite used for the nugget.
- `material`: `gold_box2d` - The physics material.

### `VariableStorageComponent`
- Stores custom variables for the entity.
- **name**: `gold_value`
- **value_int**: `200000` - This is the primary attribute defining the nugget's value.

### `ItemComponent`
- Defines the item's behavior and properties.
- `auto_pickup`: `1` - The item is automatically picked up by the player.
- `item_name`: `$item_goldnugget_200000` - The specific name for this variant.
- `stats_count_as_item_pick_up`: `0` - This pickup does not count towards item pickup statistics.
- `is_pickable`: `1` - The item can be picked up.
- `ui_sprite`: `data/ui_gfx/items/goldnugget.png` - The UI icon for the item.
- `preferred_inventory`: `FULL` - Suggests it should go into the main inventory.

### `HitboxComponent`
- Defines the collision area of the item.
- `aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`: Define the bounding box for physics interactions.

### `LifetimeComponent`
- `lifetime`: `900` - The duration in seconds the item will exist before despawning if not picked up.

### `LuaComponent` (script_item_picked_up)
- **script_item_picked_up**: `data/scripts/items/gold_pickup.lua` - This script is executed when the item is picked up, likely to add the gold value to the player.

### `LuaComponent` (script_source_file)
- **script_source_file**: `data/scripts/perks/gold_explosion.lua`
- `execute_on_added`: `1` - This script is executed immediately when the entity is added to the world.
- `remove_after_executed`: `1` - The script component is removed after execution. This likely triggers a gold explosion effect.

### `SpriteParticleEmitterComponent` (Multiple)
- These components are responsible for the visual "glitter" or particle effects around the gold nugget.
- They use various sprite files (`shine_07.xml`, `shine_08.xml`, `shine_06.xml`) with different lifetimes, emission rates, and randomization parameters to create a shimmering effect.
- Key parameters include:
    - `sprite_file`: The particle sprite.
    - `lifetime`: Duration of individual particles.
    - `emission_interval_min_frames`, `emission_interval_max_frames`: Control how often particles are emitted.
    - `count_min`, `count_max`: Number of particles emitted per interval.
    - `additive`: `1` - Particles are added to the scene, creating a glowing effect.
    - `randomize_scale`, `randomize_position`, `randomize_animation_speed_coeff`: Add variation to the particle appearance and behavior.