---
title: Suspended Radioactive Tank Prop
category: entities
---

# Suspended Radioactive Tank Prop

This document details the `suspended_tank_radioactive.xml` entity, a prop found in Noita. It represents a suspended tank filled with radioactive liquid that can be damaged, spill its contents, and explode.

## Key Components and Attributes

This entity is composed of several components that define its behavior and appearance. The most important ones are:

### PhysicsBody2Component
Defines the physical properties of the tank.

*   `is_static`: `0` - The tank is not static and can be moved.
*   `allow_sleep`: `1` - The tank can enter a sleep state when not in motion to save performance.
*   `angular_damping`: `0.01` - Controls how quickly rotational movement slows down.
*   `linear_damping`: `0.3` - Controls how quickly linear movement slows down.
*   `fixed_rotation`: `0` - The tank's rotation is not fixed and can change.

### MaterialInventoryComponent
Manages the materials contained within the tank.

*   `drop_as_item`: `0` - The tank itself does not drop as an item upon death.
*   `on_death_spill`: `1` - The tank's contents will spill out when it is destroyed.
*   `leak_on_damage_percent`: `0.999` - The tank will leak its contents when it reaches 99.9% damage.
*   `count_per_material_type`:
    *   `Material material="radioactive_liquid" count="1250"`: The tank contains 1250 units of `radioactive_liquid`.

### DamageModelComponent
Defines how the tank takes damage and its resistance.

*   `air_needed`: `0` - The tank does not require air to function or survive.
*   `blood_material`: `radioactive_liquid` - When damaged, it can spill `radioactive_liquid`.
*   `drop_items_on_death`: `0` - No specific items are dropped upon death.
*   `falling_damage_damage_max`: `2.0` - Maximum damage from falling.
*   `falling_damage_damage_min`: `0.2` - Minimum damage from falling.
*   `falling_damage_height_max`: `200` - Maximum height at which falling damage is applied.
*   `falling_damage_height_min`: `40` - Minimum height at which falling damage is applied.
*   `falling_damages`: `0` - Falling damage is not directly applied to the tank itself.
*   `fire_damage_amount`: `0.4` - Amount of damage taken from fire.
*   `fire_probability_of_ignition`: `0` - The tank cannot ignite from fire.
*   `critical_damage_resistance`: `1` - The tank has full resistance to critical damage.
*   `hp`: `0.7` - The tank has a low health pool.
*   `materials_damage`: `1` - The tank takes damage from certain materials.
*   `materials_that_damage`: `fire,lava,acid` - These materials will damage the tank.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage values for the respective materials.
*   `damage_multipliers`:
    *   `melee`: `0.1` - Melee attacks deal only 10% of their normal damage.

### PhysicsBodyCollisionDamageComponent
Applies damage to the tank when it collides with other objects at high speeds.

*   `speed_threshold`: `100.0` - Collision damage is applied if the speed exceeds 100.0.

### ExplodeOnDamageComponent
Defines the explosion behavior of the tank.

*   `explode_on_death_percent`: `1` - The tank will always explode when destroyed.
*   `explode_on_damage_percent`: `0.0` - The tank will not explode from partial damage.
*   `physics_body_modified_death_probability`: `0.9` - High probability of explosion if its physics body is modified upon death.
*   `physics_body_destruction_required`: `0.15` - The explosion is triggered if 15% of its physics body is destroyed.
*   `config_explosion`: This nested element defines the parameters of the explosion.
    *   `damage`: `2.6` - The base damage of the explosion.
    *   `camera_shake`: `40` - The intensity of camera shake during the explosion.
    *   `explosion_radius`: `40` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - The sprite used for the explosion effect.
    *   `load_this_entity`: `data/entities/particles/particle_explosion/main_green.xml` - The entity loaded for the explosion effect.
    *   `ray_energy`: `2500000` - The energy of the explosion's rays.
    *   `physics_explosion_power.min`: `1.7` - Minimum physics force applied by the explosion.
    *   `physics_explosion_power.max`: `2.3` - Maximum physics force applied by the explosion.
    *   `audio_event_name`: `explosions/barrel_sludge` - The sound event played during the explosion.

### PhysicsImageShapeComponent
Defines the visual representation and physical shape of the tank.

*   `image_file`: `data/props_gfx/suspended_tank_radioactive.png` - The image file for the tank's sprite.
*   `material`: `metal_prop` - The material of the tank's physics body.

### LuaComponent (chain_to_ceiling.lua)
This component attaches the tank to the ceiling using a script.

*   `script_source_file`: `data/scripts/props/chain_to_ceiling.lua` - The Lua script responsible for chaining.
*   `execute_on_added`: `1` - The script runs immediately when the entity is added.
*   `execute_every_n_frame`: `5` - The script executes every 5 frames.
*   `execute_times`: `-1` - The script runs indefinitely.

### VariableStorageComponent (chain generation)
These components store integer values related to the chain's position.

*   `name="chain_0_x", value_int="-1"`
*   `name="chain_0_y", value_int="-5"`

These likely represent offsets for attaching the chain to the ceiling.