---
title: Physics Pata Entity
category: entities
---

# Physics Pata Entity

This document describes the `physics_pata.xml` entity, which represents a destructible physics object that can explode and has projectile-like behavior.

## Core Components

### Base Entity

The entity inherits from `base_item_physics2.xml`, providing fundamental physics and item properties.

*   **`PhysicsBody2Component`**: Configures the physics body.
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after initialization.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and physical shape.
    *   `image_file`: Specifies the sprite for the object (`data/props_gfx/pata.png`).
    *   `material`: Sets the physical material type (`rock_box2d_hard`).

### Material Inventory

This component manages the materials contained within the entity, particularly for its explosive properties.

*   **`MaterialInventoryComponent`**:
    *   `drop_as_item`: Set to `0`, indicating it doesn't drop as a usable item upon death.
    *   `on_death_spill`: Set to `1`, meaning its contents spill out when destroyed.
    *   `leak_on_damage_percent`: Set to `0.5`, causing it to leak when 50% damaged.
    *   `audio_collision_size_modifier_amount`: `0.8`, affecting collision sound properties.
    *   **`count_per_material_type`**: Defines the materials and their quantities.
        *   `Material material="gunpowder_explosive" count="300"`: Contains 300 units of explosive gunpowder.

### Damage Model

This component handles how the entity takes damage and reacts to environmental factors.

*   **`DamageModelComponent`**:
    *   `air_needed`: `0`, does not require air to function.
    *   `blood_material`: `oil`, the material that spills when damaged.
    *   `drop_items_on_death`: `0`, does not drop items on death.
    *   `falling_damage_damage_max`: `1.2`, maximum damage from falling.
    *   `falling_damage_damage_min`: `0.1`, minimum damage from falling.
    *   `falling_damage_height_max`: `250`, maximum height for falling damage.
    *   `falling_damage_height_min`: `70`, minimum height for falling damage.
    *   `falling_damages`: `0`, falling damage is not directly applied as a primary mechanic.
    *   `fire_damage_amount`: `0.4`, damage taken from fire.
    *   `fire_probability_of_ignition`: `0`, cannot ignite from fire.
    *   `critical_damage_resistance`: `1`, high resistance to critical damage.
    *   `hp`: `100.2`, hit points of the entity.
    *   `materials_damage`: `1`, can be damaged by certain materials.
    *   `materials_that_damage`: `fire,lava,acid`, materials that inflict damage.
    *   `materials_how_much_damage`: `0.0002,0.0001,0.001`, the damage values for the respective materials.
    *   **`damage_multipliers`**:
        *   `melee`: `0.1`, reduced damage from melee attacks.

### Explosion Component

This component defines the entity's explosive behavior.

*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: `1`, always explodes upon death.
    *   `explode_on_damage_percent`: `0.0`, does not explode solely from damage percentage.
    *   `physics_body_modified_death_probability`: `0.4`, 40% chance to explode when its physics body is modified upon death.
    *   `physics_body_destruction_required`: `0.5`, requires 50% destruction of its physics body to trigger explosion conditions.
    *   **`config_explosion`**: Detailed configuration for the explosion effect.
        *   `damage`: `2.6`, the base damage of the explosion.
        *   `camera_shake`: `40`, intensity of camera shake.
        *   `explosion_radius`: `45`, the radius of the explosion.
        *   `explosion_sprite`: `data/particles/explosion_032.xml`, the particle effect for the explosion.
        *   `explosion_sprite_lifetime`: `10`, duration of the explosion sprite.
        *   `create_cell_probability`: `80`, 80% chance to create material cells.
        *   `hole_enabled`: `1`, creates holes in terrain.
        *   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_medium.xml`, the entity to load for the explosion.
        *   `ray_energy`: `4000000`, energy of the explosion's rays.
        *   `physics_explosion_power.min`: `1.9`, minimum physics force applied by the explosion.
        *   `physics_explosion_power.max`: `2.5`, maximum physics force applied by the explosion.
        *   `physics_throw_enabled`: `1`, objects are thrown by the explosion.
        *   `sparks_count_min`: `10`, minimum number of sparks.
        *   `sparks_count_max`: `25`, maximum number of sparks.
        *   `stains_radius`: `15`, radius of stains left by the explosion.
        *   `delay.min`: `1`, minimum delay before explosion.
        *   `delay.max`: `4`, maximum delay before explosion.
        *   `audio_event_name`: `explosions/barrel_oil`, the sound event for the explosion.

## Scripting Components

### Lua Components

These components enable custom scripting for the entity's behavior.

*   **`LuaComponent` (pata_inactive)**:
    *   `_tags`: `pata_inactive`, identifies this state.
    *   `execute_every_n_frame`: `-1`, executes only when triggered.
    *   `script_damage_received`: `data/scripts/props/pata_activate.lua`, script executed when damage is received to activate the entity.

*   **`LuaComponent` (pata_active)**:
    *   `_enabled`: `0`, initially disabled.
    *   `_tags`: `pata_active`, identifies this state.
    *   `execute_every_n_frame`: `40`, executes every 40 frames.
    *   `script_source_file`: `data/scripts/props/pata_shoot.lua`, script for shooting behavior.

## Audio Components

### Audio Loop Component

*   **`AudioLoopComponent`**:
    *   `_tags`: `sound_spray`, associated tag for sound.
    *   `file`: `data/audio/Desktop/materials.bank`, audio bank file.
    *   `event_name`: `materials/spray`, the audio event name.
    *   `volume_autofade_speed`: `0.25`, speed at which volume fades automatically.

### Audio Component

*   **`AudioComponent`**:
    *   `file`: `data/audio/Desktop/materials.bank`, audio bank file.
    *   `event_root`: `collision/metalhollow`, root event for collision sounds.
    *   `set_latest_event_position`: `1`, sets the sound position to the latest event.

## Variable Storage

### Variable Storage Component

*   **`VariableStorageComponent`**:
    *   `_tags`: `pata_times_shot`, tag for tracking shots.
    *   `name`: `pata_times_shot`, the name of the variable.
    *   `value_int`: `0`, initial integer value.