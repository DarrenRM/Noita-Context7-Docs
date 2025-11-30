---
title: Suspended Seamine Prop
category: entities
---

# Suspended Seamine Prop

This document details the configuration of the Suspended Seamine entity in Noita, designed for AI-assisted modding.

## Overview

The Suspended Seamine is a prop entity that hangs from the ceiling and explodes when damaged or when its physics body is sufficiently modified. It contains a volatile liquid that spills upon death.

## Key Components and Attributes

### Entity Tags

*   `hittable`: Can be damaged by projectiles and other means.
*   `teleportable_NOT`: Cannot be teleported.
*   `prop`: Identifies it as a prop object.
*   `prop_physics`: It has physics properties.
*   `mortal`: Required for it to be able to explode.

### PhysicsBody2Component

Controls the physical behavior of the seamine.

*   `is_static`: `0` (not static, can move).
*   `allow_sleep`: `1` (can enter a sleep state to save performance).
*   `linear_damping`: `0.3` (resistance to linear motion).
*   `angular_damping`: `0.01` (resistance to rotational motion).

### PhysicsImageShapeComponent

Defines the visual representation and collision shape.

*   `image_file`: `data/props_gfx/seamine.png` (The sprite used for the seamine).
*   `material`: `metal_rust` (The material for physics interactions).

### MaterialInventoryComponent

Manages the materials contained within the seamine.

*   `on_death_spill`: `1` (Spills its contents when destroyed).
*   `leak_on_damage_percent`: `0.5` (Starts leaking when 50% damaged).
*   `count_per_material_type`:
    *   `Material material="liquid_fire" count="300"` (Contains 300 units of liquid fire).

### DamageModelComponent

Handles how the seamine takes damage and its reactions.

*   `hp`: `0.3` (Very low health, easily destroyed).
*   `falling_damage_damage_max`: `1.2` (Maximum damage from falling).
*   `falling_damage_height_max`: `250` (Height at which max falling damage is applied).
*   `fire_damage_amount`: `0.4` (Damage taken from fire).
*   `materials_that_damage`: `fire,lava,acid` (Materials that can damage the seamine).
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` (Damage values for the respective materials).
*   `damage_multipliers`:
    *   `melee`: `0.1` (Takes only 10% damage from melee attacks).

### ExplodeOnDamageComponent

Manages the explosion behavior.

*   `explode_on_death_percent`: `1` (Guaranteed to explode upon death).
*   `physics_body_modified_death_probability`: `0.8` (80% chance to explode if physics body is sufficiently modified upon death).
*   `physics_body_destruction_required`: `0.25` (Explosion is triggered if 25% of its physics body is destroyed).
*   `config_explosion`:
    *   `damage`: `2.8` (Damage dealt by the explosion).
    *   `camera_shake`: `40` (Intensity of camera shake).
    *   `explosion_radius`: `50` (Radius of the explosion).
    *   `ray_energy`: `700000` (Energy of the explosion's rays).
    *   `physics_explosion_power.min`: `1.9` (Minimum physics force applied by the explosion).
    *   `physics_explosion_power.max`: `2.5` (Maximum physics force applied by the explosion).
    *   `delay.min`: `1` (Minimum delay before explosion).
    *   `delay.max`: `4` (Maximum delay before explosion).

### LuaComponent (Death Script)

*   `script_death`: `data/scripts/debug/seamine_death.lua` (Custom script executed on death).

### LuaComponent (Chain Generation)

*   `script_source_file`: `data/scripts/props/chain_to_ceiling.lua` (Script responsible for attaching the seamine to the ceiling).
*   `execute_on_added`: `1` (Runs immediately when the entity is added).
*   `execute_every_n_frame`: `5` (Runs every 5 frames).
*   `execute_times`: `-1` (Runs indefinitely).

### VariableStorageComponent (Chain Generation)

These components store offset values for the chain attachment.

*   `name`: `chain_0_x`, `value_int`: `-1`
*   `name`: `chain_0_y`, `value_int`: `-7`