---
title: Base Prop Crystal Red
category: entities
---

# Base Prop Crystal Red

This document describes the `base_prop_crystal.xml` entity, which defines a red crystal prop in Noita. This entity is designed to be a destructible object that can explode and release particles.

## Key Components and Attributes

### Base Entity Structure

The entity inherits from `data/entities/base_item_physics2.xml`, indicating it's a physics-based item.

### Physics Components

*   **`PhysicsBody2Component`**: Manages the physical properties of the crystal.
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity does not self-destruct immediately after spawning.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape.
    *   `image_file`: `data/props_gfx/crystal_red.png` - Specifies the sprite for the crystal.
    *   `material`: `crystal_solid` - The material type for physics interactions.

### Behavior Components

*   **`VelocityComponent`**: Standard component for velocity.
*   **`LuaComponent`**: Attaches custom Lua scripting for behavior.
    *   `script_source_file`: `data/scripts/props/crystal_rotate.lua` - This script likely handles the crystal's rotation or hovering effect.
    *   `execute_every_n_frame`: `3` - The script runs every 3 frames.

### Material and Damage Handling

*   **`MaterialInventoryComponent`**: Manages the materials contained within the crystal and how they are released.
    *   `drop_as_item`: `0` - The crystal does not drop as a usable item upon death.
    *   `on_death_spill`: `1` - Materials spill out when the entity dies.
    *   `leak_on_damage_percent`: `0.1` - Starts leaking when 10% of its health is lost.
    *   `kill_when_empty`: `1` - The entity is destroyed when its material inventory is depleted.
    *   **`count_per_material_type`**:
        *   `Material material="spark_red" count="300"`: Contains 300 units of `spark_red` material.

*   **`DamageModelComponent`**: Defines how the crystal takes damage and reacts.
    *   `hp`: `10` - The crystal has 10 hit points.
    *   `materials_that_damage`: `fire,lava,acid` - These materials inflict damage.
    *   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage amounts for fire, lava, and acid respectively.
    *   `falling_damages`: `0` - Does not take damage from falling.
    *   `fire_damage_amount`: `0.4` - Base fire damage.
    *   `critical_damage_resistance`: `1` - No resistance to critical damage.

### Explosion Behavior

*   **`ExplodeOnDamageComponent`**: Controls the explosion mechanics.
    *   `explode_on_death_percent`: `1` - Always explodes upon death.
    *   `physics_body_modified_death_probability`: `0.9` - High chance of physics body modification upon death.
    *   `physics_body_destruction_required`: `0.15` - Requires 15% of its physics body to be destroyed before triggering certain death effects.
    *   **`config_explosion`**: Defines the explosion parameters.
        *   `damage`: `2.6` - The damage dealt by the explosion.
        *   `camera_shake`: `20` - Intensity of camera shake.
        *   `explosion_radius`: `25` - The radius of the explosion.
        *   `explosion_sprite`: `data/particles/explosion_032.xml` - Visual effect for the explosion.
        *   `load_this_entity`: `data/entities/particles/particle_explosion/main_swirly_red.xml,data/entities/props/crystal_red_effect.xml` - Entities spawned by the explosion.
        *   `ray_energy`: `4000000` - Energy for raycasting effects.
        *   `physics_explosion_power.min`/`max`: `1.9`/`2.5` - The force of the physics-based explosion.
        *   `audio_event_name`: `explosions/magic_rocket_big` - The sound effect for the explosion.

### Particle Emission

*   **`ParticleEmitterComponent`**: Manages the emission of particles.
    *   `emitted_material_name`: `spark_red` - The material of the emitted particles.
    *   `gravity.y`: `-60.0` - Downward gravity for particles.
    *   `lifetime_min`/`max`: `0.8`/`1.6` - Particle lifespan.
    *   `count_min`/`max`: `1`/`1` - Emits one particle at a time.
    *   `emission_interval_min_frames`/`max_frames`: `1`/`1` - Emits particles every frame.

### Visual and Audio

*   **`LightComponent`**: Adds a light source.
    *   `radius`: `60` - The radius of the light.
    *   `r`, `g`, `b`: `255`, `20`, `20` - Reddish light color.
*   **`AudioLoopComponent`**: Plays a looping sound effect.
    *   `event_name`: `animals/magical/movement_loop` - The name of the audio event.