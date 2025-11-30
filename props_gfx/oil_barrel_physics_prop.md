---
title: Oil Barrel (Physics Prop)
category: data/entities
---

# Oil Barrel (Physics Prop)

This document describes the `physics_barrel_oil.xml` entity, which represents a physics-enabled barrel filled with oil in Noita. It's designed to be a destructible prop that can spill its contents and explode.

## Key Components and Attributes

### Base Entity (`Base`)

This component inherits functionality from `base_item_physics2.xml`, providing core physics and item-related properties.

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after initialization.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and physical shape.
    *   `image_file`: `data/props_gfx/barrel_unstable.png` - The sprite used for the barrel.
    *   `material`: `metal_rust_barrel` - The material type for physics interactions.

### Material Inventory (`MaterialInventoryComponent`)

This component manages the liquid contents of the barrel.

*   `drop_as_item`: Set to `0`, so the barrel itself doesn't drop as an item on death.
*   `on_death_spill`: Set to `1`, meaning the contents will spill out when the entity is destroyed.
*   `leak_on_damage_percent`: Set to `0.5`, causing the barrel to leak when it reaches 50% damage.
*   `audio_collision_size_modifier_amount`: `0.8` - Affects the sound of collisions.
*   **`count_per_material_type`**:
    *   `Material material="oil" count="300"`: The barrel contains 300 units of "oil".

### Damage Model (`DamageModelComponent`)

This component defines how the barrel takes damage and reacts to it.

*   `air_needed`: `0` - Does not require air to function.
*   `blood_material`: `oil` - When damaged, it can spill "oil".
*   `drop_items_on_death`: `0` - No specific items are dropped on death, beyond its contents.
*   `falling_damage_damage_max`: `1.2`
*   `falling_damage_damage_min`: `0.1`
*   `falling_damage_height_max`: `250`
*   `falling_damage_height_min`: `70`
*   `falling_damages`: `0` - Falling itself doesn't directly cause damage to the barrel.
*   `fire_damage_amount`: `0.4` - Amount of damage taken from fire.
*   `fire_probability_of_ignition`: `0` - Cannot ignite directly from fire.
*   `critical_damage_resistance`: `1` - High resistance to critical damage.
*   `hp`: `0.2` - Very low health, making it easy to destroy.
*   `materials_damage`: `1` - Can be damaged by certain materials.
*   `materials_that_damage`: `fire,lava,acid` - Materials that can damage the barrel.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage multipliers for the respective materials.
*   **`damage_multipliers`**:
    *   `melee`: `0.1` - Reduced damage taken from melee attacks.

### Explosion on Damage (`ExplodeOnDamageComponent`)

This component governs the barrel's explosive behavior.

*   `explode_on_death_percent`: `1` - Will always explode upon death.
*   `explode_on_damage_percent`: `0.0` - Does not explode from partial damage.
*   `physics_body_destruction_required`: `0.15` - Requires 15% of its physics body to be destroyed before it can explode.
*   `physics_body_modified_death_probability`: `0.9` - If the destruction threshold is met upon death, there's a 90% chance it will explode.
*   **`config_explosion`**: Defines the parameters of the explosion.
    *   `damage`: `2.6` - The base damage dealt by the explosion.
    *   `camera_shake`: `40` - The intensity of camera shake.
    *   `explosion_radius`: `45` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The particle effect for the explosion.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_medium.xml` - The entity to load for the explosion effect.
    *   `hole_enabled`: `1` - Creates holes in terrain.
    *   `ray_energy`: `4000000` - Energy for physics-based destruction.
    *   `physics_explosion_power.min`: `1.9`
    *   `physics_explosion_power.max`: `2.5`
    *   `shake_vegetation`: `1` - Shakes vegetation in the area.
    *   `sparks_enabled`: `1` - Creates sparks.
    *   `stains_enabled`: `1` - Creates stains on surfaces.
    *   `delay.min`: `1`
    *   `delay.max`: `4`
    *   `audio_event_name`: `explosions/barrel_oil` - The sound event for the explosion.

### Audio Components

*   **`AudioLoopComponent`**:
    *   `_tags`: `sound_spray` - Associated with spraying sounds.
    *   `event_name`: `materials/spray` - The specific audio event.
*   **`AudioComponent`**:
    *   `event_root`: `collision/metalhollow` - The root event for collision sounds.
    *   `set_latest_event_position`: `1` - Sets the sound position to the latest event.