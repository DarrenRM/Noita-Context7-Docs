---
title: Potion Item Base Entity
category: entities/items/pickup
---

# Potion Item Base Entity

This document describes the base entity for potions in Noita, serving as a template for various potion types. It defines the physical properties, interaction logic, and visual representation of a potion.

## Key Components

### Physics Components

These components define the physical behavior of the potion in the game world.

*   **`PhysicsBodyComponent`**:
    *   `allow_sleep`: `1` - Allows the physics body to sleep when not in motion.
    *   `is_bullet`: `1` - Treats the object as a bullet for collision detection.
    *   `hax_fix_going_through_ground`: `1` - A fix to prevent the potion from falling through the ground.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/items_gfx/potion_normals.png` - The texture used for the potion's physical shape.
    *   `material`: `potion_glass_box2d` - The physics material defining its interaction with other objects.
*   **`PhysicsThrowableComponent`**:
    *   `max_throw_speed`: `180` - The maximum speed the potion can be thrown.
    *   `throw_force_coeff`: `1.5` - Coefficient for calculating throw force.
*   **`ProjectileComponent`**:
    *   `lifetime`: `-1` - The projectile will not despawn on its own.
    *   `penetrate_entities`: `1` - Allows the projectile to pass through other entities.
*   **`VelocityComponent`**:
    *   Defines the potion's velocity.

### Potion Logic Components

These components handle the core functionality and interactions of potions.

*   **`LuaComponent` (script_source_file)**:
    *   `script_source_file`: `data/scripts/items/potion.lua` - The main script for potion behavior.
    *   `execute_on_added`: `1` - Executes the script when the entity is added.
    *   `remove_after_executed`: `1` - Removes the component after execution.
*   **`LuaComponent` (script_item_picked_up)**:
    *   `script_item_picked_up`: `data/scripts/items/potion_effect.lua` - Script executed when the potion is picked up.
*   **`LuaComponent` (script_death)**:
    *   `script_death`: `data/scripts/items/potion_glass_break.lua` - Script executed when the potion is destroyed.
*   **`PotionComponent`**:
    *   `spray_velocity_coeff`: `75` - Coefficient for spray velocity.
    *   `spray_velocity_normalized_min`: `0.75` - Minimum normalized spray velocity.
    *   `dont_spray_static_materials`: `1` - Prevents spraying on static materials.
    *   `dont_spray_just_leak_gas_materials`: `1` - Prevents spraying on materials that only leak gas.
*   **`MaterialSuckerComponent`**:
    *   `barrel_size`: `1000` - The size of the "sucker" for materials.
    *   `num_cells_sucked_per_frame`: `5` - How many material cells are sucked per frame.
*   **`MaterialInventoryComponent`**:
    *   `on_death_spill`: `1` - The potion's contents spill upon death.
    *   `leak_pressure_min`: `0.07` - Minimum pressure for leaking.
    *   `leak_on_damage_percent`: `1` - Leaks when damaged.
    *   `min_damage_to_leak`: `0.0` - Leaks even with minimal damage.
    *   `death_throw_particle_velocity_coeff`: `0.5` - Velocity coefficient for particles when the potion dies.
    *   `do_reactions`: `20` - Number of reactions to perform.
    *   `do_reactions_explosions`: `1` - Enables reactions that cause explosions.
    *   `do_reactions_entities`: `1` - Enables reactions that affect entities.
*   **`DamageModelComponent`**:
    *   `hp`: `0.5` - The potion's hit points.
    *   `fire_damage_amount`: `0.2` - Amount of fire damage it can inflict.
    *   `materials_damage`: `1` - Allows the potion to damage entities through materials.
    *   `materials_that_damage`: `lava` - Materials that can damage the potion.
    *   `materials_how_much_damage`: `0.001` - How much damage these materials inflict.
*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: `1` - Explodes when destroyed.
    *   `physics_body_destruction_required`: `0.51` - The destruction threshold for the physics body to trigger an explosion.
    *   `config_explosion`: Defines the properties of the explosion.
        *   `damage`: `0` - Base damage of the explosion.
        *   `camera_shake`: `10` - Intensity of camera shake.
        *   `explosion_radius`: `3` - The radius of the explosion.
        *   `ray_energy`: `100000` - Energy of the explosion's rays.
        *   `physics_explosion_power.max`: `5` - Maximum physics force of the explosion.
        *   `sparks_enabled`: `1` - Sparks are generated.
        *   `spark_material`: `glass` - The material of the sparks.
        *   `stains_enabled`: `1` - Stains are left by the explosion.
*   **`PhysicsBodyCollisionDamageComponent`**:
    *   `speed_threshold`: `80.0` - The speed at which collisions cause damage.

### Item Components

These components define the potion as an item that can be interacted with by the player.

*   **`SpriteComponent`**:
    *   `image_file`: `data/items_gfx/potion.png` - The sprite displayed when the potion is held.
    *   `_enabled`: `0` - This sprite is disabled by default and likely overridden by specific potion types.
*   **`ItemComponent`**:
    *   `item_name`: `$item_potion` - The internal name of the item.
    *   `is_pickable`: `1` - The item can be picked up.
    *   `is_equipable_forced`: `1` - The item is forced to be equipped.
    *   `ui_sprite`: `data/ui_gfx/items/potion.png` - The sprite displayed in the UI.
    *   `ui_description`: `$item_description_potion` - The description shown in the UI.
    *   `preferred_inventory`: `QUICK` - The preferred inventory slot.
*   **`AbilityComponent`**:
    *   `ui_name`: `$item_potion_with_material` - The UI name when a material is added.
    *   `throw_as_item`: `1` - Allows the potion to be thrown as an item.
*   **`UIInfoComponent`**:
    *   `name`: `""` - Placeholder for the potion's name.

### Visual and Audio Components

*   **`SpriteParticleEmitterComponent`**:
    *   Defines particle effects, likely for visual flair or when the potion is used/broken.
    *   `sprite_file`: `data/particles/ray.xml` - The particle sprite.
    *   `color.r`, `color.g`, `color.b`, `color.a`: Defines the initial color.
    *   `color_change`: Defines how the color changes over time.
    *   `velocity`, `gravity`: Defines particle movement.
    *   `scale`, `scale_velocity`: Defines particle scaling.
    *   `emissive`, `additive`: Affects how particles are rendered.
*   **`AudioLoopComponent`**:
    *   `file`: `data/audio/Desktop/materials.bank` - The audio bank.
    *   `event_name`: `materials/spray_potion` - The audio event for spraying.
*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/materials.bank` - The audio bank.
    *   `event_root`: `collision/glass_potion` - The audio event for potion collision.