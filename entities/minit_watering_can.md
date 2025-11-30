---
title: Minit Watering Can
category: entities
---

---

# Minit Watering Can

This document details the Noita entity configuration for the "Minit Watering Can" item. It functions as a projectile that can suck up and spray materials.

## Core Components

### Physics and Collision

*   **`PhysicsBodyComponent`**: Defines the physical properties of the watering can, allowing it to interact with the game world.
    *   `is_bullet="1"`: Indicates it can be a projectile.
    *   `on_death_leave_physics_body="1"`: Ensures its physics body persists even after destruction.
*   **`PhysicsImageShapeComponent`**: Renders the visual representation of the watering can using `data/items_gfx/minit_watering_can.png`.
*   **`PhysicsThrowableComponent`**: Enables the item to be thrown with specific force and speed.
    *   `max_throw_speed="180"`
    *   `throw_force_coeff="1.5"`
*   **`ProjectileComponent`**: Configures the item as a projectile.
    *   `lifetime="-1"`: The projectile does not despawn on its own.
    *   `penetrate_entities="1"`: Can pass through other entities.
*   **`VelocityComponent`**: Manages the projectile's velocity.
*   **`PhysicsBodyCollisionDamageComponent`**: Deals damage upon collision if a certain speed threshold is met.
    *   `speed_threshold="80.0"`

### Potion and Material Interaction

*   **`LuaComponent` (script_source_file)**: Executes `data/scripts/items/potion.lua` when added, handling core potion logic.
*   **`LuaComponent` (script_item_picked_up)**: Executes `data/scripts/items/potion_effect.lua` when the item is picked up.
*   **`PotionComponent`**: Governs the spraying behavior of the potion.
    *   `spray_velocity_coeff="75"`
    *   `spray_velocity_normalized_min="0.75"`
    *   `body_colored="1"`: The sprayed material will inherit the color of the watering can.
*   **`MaterialSuckerComponent`**: Allows the watering can to absorb materials.
    *   `barrel_size="1000"`: The capacity for material absorption.
    *   `num_cells_sucked_per_frame="5"`: How many material cells are absorbed each frame.
*   **`MaterialInventoryComponent`**: Manages the materials stored within the watering can.
    *   `on_death_spill="1"`: Materials are spilled upon death.
    *   `leak_pressure_min="0.07"` / `leak_pressure_min="0.1"`: Defines pressure thresholds for leaking.
    *   `leak_on_damage_percent="1"`: Leaks when damaged.
    *   `min_damage_to_leak="0.0"`: Any damage can cause a leak.
    *   `death_throw_particle_velocity_coeff="0.5"`: Velocity of particles when spilling on death.

### Damage and Destruction

*   **`DamageModelComponent`**: Defines the health and damage resistances of the watering can.
    *   `hp="0.5"`: Low health.
    *   `fire_damage_amount="0.2"`: Takes fire damage.
    *   `materials_damage="1"`: Can be damaged by certain materials.
    *   `materials_that_damage="lava"`: Specifically damaged by lava.
*   **`ExplodeOnDamageComponent`**: Configures the watering can to explode under certain conditions.
    *   `explode_on_death_percent="1"`: Explodes when destroyed.
    *   `physics_body_destruction_required="0.51"`: Explosion triggered when 51% of the physics body is destroyed.
    *   `config_explosion`: Details of the explosion effect, including damage, radius, and particle effects.

### Item Properties

*   **`SpriteComponent`**: Renders the watering can when held in hand.
    *   `image_file="data/items_gfx/minit_watering_can.png"`
*   **`ItemComponent`**: Defines the item's behavior in the inventory and world.
    *   `item_name="Potion"`: Internal name.
    *   `is_pickable="1"`: Can be picked up.
    *   `is_equipable_forced="1"`: Can be equipped directly.
    *   `ui_sprite="data/items_gfx/minit_watering_can.png"`: Icon for UI.
    *   `ui_description="Equip and throw."`: Tooltip description.
*   **`AbilityComponent`**: Grants abilities to the item, such as throwing.
    *   `throw_as_item="1"`: Can be thrown as an item.
*   **`UIInfoComponent`**: Provides information for the UI.
    *   `name="Watering can"`: Display name.

### Visual and Audio Effects

*   **`SpriteParticleEmitterComponent`**: Creates particle effects, likely for the spraying action.
    *   `sprite_file="data/particles/ray.xml"`: Uses a ray-like particle.
    *   `lifetime="1.5"`: Particle duration.
    *   `emissive="1"`, `additive="1"`: For glowing effects.
*   **`AudioLoopComponent`**: Plays a looping sound effect when spraying.
    *   `file="data/audio/Desktop/materials.bank"`
    *   `event_name="materials/spray_potion"`
*   **`AudioComponent`**: Plays a sound effect on collision.
    *   `file="data/audio/Desktop/materials.bank"`
    *   `event_root="collision/glass_potion"`