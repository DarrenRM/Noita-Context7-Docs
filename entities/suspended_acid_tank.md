---
title: Suspended Acid Tank
category: entities
---

# Suspended Acid Tank

This entity represents a suspended tank filled with acid. It's a prop that can be interacted with, damaged, and will explode when destroyed or heavily damaged.

## Key Components and Attributes

### `PhysicsBody2Component`

Controls the physical behavior of the tank.

*   `is_static`: `0` - The tank is not fixed in place and can move.
*   `allow_sleep`: `1` - The tank can enter a sleep state to save performance when not in motion.
*   `linear_damping`: `0.3` - Reduces linear velocity over time.
*   `angular_damping`: `0.01` - Reduces rotational velocity over time.

### `MaterialInventoryComponent`

Manages the materials contained within the tank.

*   `drop_as_item`: `0` - The tank itself does not drop as an item upon death.
*   `on_death_spill`: `1` - When the tank dies, its contents will spill out.
*   `leak_on_damage_percent`: `0.999` - The tank will leak its contents when it reaches 99.9% damage.
*   `count_per_material_type`:
    *   `Material material="acid" count="1250"`: The tank contains 1250 units of acid.

### `DamageModelComponent`

Defines how the tank takes damage and its properties related to damage.

*   `hp`: `0.7` - The tank has a low health pool.
*   `falling_damages`: `0` - The tank does not take damage from falling.
*   `fire_damage_amount`: `0.4` - The amount of damage taken from fire.
*   `fire_probability_of_ignition`: `0` - The tank cannot ignite.
*   `materials_that_damage`: `fire,lava` - Materials that can damage the tank.
*   `materials_how_much_damage`: `0.0002,0.0001` - The damage multiplier for fire and lava respectively.
*   `critical_damage_resistance`: `1` - No resistance to critical damage.
*   `blood_material`: `acid` - When damaged, it behaves as if it's bleeding acid.

### `PhysicsBodyCollisionDamageComponent`

Applies damage to the tank based on physics collisions.

*   `speed_threshold`: `100.0` - The speed at which collisions start to deal damage.

### `ExplodeOnDamageComponent`

Handles the explosion behavior of the tank.

*   `explode_on_death_percent`: `1` - The tank will explode when it reaches 100% damage.
*   `explode_on_damage_percent`: `0.0` - The tank will not explode from partial damage.
*   `physics_body_modified_death_probability`: `0.9` - High probability of explosion if its physics body is modified upon death.
*   `physics_body_destruction_required`: `0.15` - Requires 15% of its physics body to be destroyed for potential explosion.
*   `config_explosion`:
    *   `damage`: `2.6` - The damage dealt by the explosion.
    *   `camera_shake`: `40` - The intensity of camera shake during the explosion.
    *   `explosion_radius`: `40` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The visual effect for the explosion.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_green.xml` - The entity to load for the explosion effect.
    *   `ray_energy`: `2500000` - The energy of the explosion's rays.
    *   `physics_explosion_power.min`: `1.7` - Minimum physics force applied by the explosion.
    *   `physics_explosion_power.max`: `2.3` - Maximum physics force applied by the explosion.
    *   `audio_event_name`: `explosions/barrel_sludge` - The sound effect played during the explosion.

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the tank.

*   `image_file`: `data/props_gfx/suspended_tank_acid.png` - The sprite file for the tank.
*   `material`: `metal_prop` - The material type for collision and physics.

### `LuaComponent`

Attaches a Lua script to the entity for custom behavior.

*   `script_source_file`: `data/scripts/props/chain_to_ceiling.lua` - The script responsible for attaching the tank to a chain.
*   `execute_on_added`: `1` - The script runs when the entity is added to the world.
*   `execute_every_n_frame`: `5` - The script executes every 5 frames.
*   `execute_times`: `-1` - The script runs indefinitely.

### `VariableStorageComponent`

Stores variables for the Lua script.

*   `name`: `chain_0_x`, `chain_0_y` - Variables used by the `chain_to_ceiling.lua` script to define the chain's attachment points.
*   `value_int`: `-1`, `-5` - The integer values for the chain attachment points.