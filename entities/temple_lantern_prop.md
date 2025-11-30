---
title: Temple Lantern Prop
category: entities
---

---

# Temple Lantern Prop

This document details the `temple_lantern.xml` entity, a prop found in Noita. It's a physics-enabled object that emits light and particles, and can explode when damaged.

## Key Components and Attributes

### PhysicsBody2Component
Manages the physical properties of the lantern.

*   `allow_sleep`: `1` - Allows the physics body to go to sleep when inactive.
*   `angular_damping`: `0.01` - Resistance to rotational movement.
*   `linear_damping`: `0.3` - Resistance to linear movement.
*   `init_offset_x`: `9` - Initial offset for physics body positioning.
*   `root_offset_x`: `4` - Offset for the root of the physics body.
*   `root_offset_y`: `7` - Offset for the root of the physics body.

### MaterialInventoryComponent
Defines the materials contained within the lantern.

*   `drop_as_item`: `0` - The lantern does not drop as an item upon death.
*   `on_death_spill`: `1` - Materials spill out when the lantern is destroyed.
*   `leak_on_damage_percent`: `0.999` - Leaks materials when 99.9% damaged.
*   `count_per_material_type`:
    *   `Material material="plasma_fading" count="16"`: Contains 16 units of `plasma_fading` material.

### DamageModelComponent
Handles how the lantern takes damage and its consequences.

*   `air_needed`: `0` - Does not require air to function.
*   `blood_material`: `plasma_fading` - The material that spills when damaged.
*   `drop_items_on_death`: `0` - Does not drop items on death.
*   `falling_damage_damage_max`: `1.2` - Maximum damage from falling.
*   `falling_damage_damage_min`: `0.1` - Minimum damage from falling.
*   `falling_damage_height_max`: `250` - Maximum height for falling damage calculation.
*   `falling_damage_height_min`: `70` - Minimum height for falling damage calculation.
*   `falling_damages`: `0` - Falling damage is not directly applied as a damage type.
*   `fire_damage_amount`: `0.2` - Amount of damage from fire.
*   `fire_probability_of_ignition`: `0` - Cannot ignite from fire.
*   `hp`: `0.15` - Hit points of the lantern.
*   `is_on_fire`: `0` - Starts not on fire.
*   `critical_damage_resistance`: `1` - High resistance to critical damage.
*   `ui_report_damage`: `0` - Does not report damage to the UI.

### ExplodeOnDamageComponent
Defines the explosion behavior when the lantern is damaged.

*   `explode_on_death_percent`: `1` - Explodes when health reaches 0%.
*   `explode_on_damage_percent`: `0.0` - Can explode even with minimal damage.
*   `physics_body_modified_death_probability`: `0.75` - Probability of explosion if physics body is modified upon death.
*   `physics_body_destruction_required`: `0.5` - Requires 50% destruction of physics body to trigger explosion.
*   `config_explosion`:
    *   `damage`: `0.2` - Damage dealt by the explosion.
    *   `camera_shake`: `1` - Causes camera shake.
    *   `explosion_radius`: `5` - Radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_008.xml` - Sprite used for the explosion effect.
    *   `create_cell_probability`: `50` - 50% chance to create cells.
    *   `hole_enabled`: `1` - Creates a hole in the environment.
    *   `ray_energy`: `10000` - Energy of the explosion rays.
    *   `damage_mortals`: `1` - Deals damage to living entities.
    *   `physics_explosion_power.min`: `0.05` - Minimum physics force applied by the explosion.
    *   `physics_explosion_power.max`: `0.1` - Maximum physics force applied by the explosion.
    *   `sparks_enabled`: `1` - Creates sparks.
    *   `stains_enabled`: `1` - Creates stains.

### PhysicsBodyCollisionDamageComponent
Applies damage to the lantern when it collides with objects at high speed.

*   `speed_threshold`: `85.0` - Collision speed required to deal damage.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape of the lantern.

*   `image_file`: `data/props_gfx/temple_lantern_01.png` - The sprite file for the lantern.
*   `material`: `metal_nohit` - The material of the sprite, which cannot be hit directly.

### LightComponent
Adds a light source to the lantern.

*   `radius`: `128` - The radius of the light.
*   `fade_out_time`: `1.5` - Time it takes for the light to fade out.
*   `r`, `g`, `b`: `30`, `30`, `255` - Sets the light color to blue.

### LuaComponent
Attaches a Lua script for custom behavior.

*   `script_source_file`: `data/scripts/props/temple_lantern.lua` - The script controlling the lantern's behavior.
*   `execute_on_added`: `1` - The script runs when the entity is added.
*   `execute_every_n_frame`: `5` - The script executes every 5 frames.
*   `execute_times`: `-1` - The script runs indefinitely.

### ParticleEmitterComponent
Emits particles from the lantern.

*   `emitted_material_name`: `plasma_fading_bright` - The material of the emitted particles.
*   `lifetime_min`, `lifetime_max`: `1.0`, `5.0` - Duration the particles exist.
*   `count_min`, `count_max`: `1`, `2` - Number of particles emitted per burst.
*   `gravity.y`: `-15` - Downward gravity applied to particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `10`, `90` - Interval between particle emissions.
*   `is_emitting`: `1` - The emitter is active.

### SpriteParticleEmitterComponent
Emits sprite-based particles.

*   `sprite_file`: `data/particles/tinyspark_03.xml` - The sprite file for these particles.
*   `additive`: `1` - Particles use additive blending.
*   `gravity.y`: `-30` - Stronger downward gravity for these sparks.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `9`, `9` - Emits sparks every 9 frames.
*   `count_min`, `count_max`: `1`, `1` - Emits one spark at a time.