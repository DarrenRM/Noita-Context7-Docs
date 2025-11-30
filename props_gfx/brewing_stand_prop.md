---
title: Brewing Stand Prop
category: data
---

```

# Brewing Stand Prop

This document details the `physics_brewing_stand.xml` entity, which represents a brewing stand prop in Noita. It's a physics-enabled object that can hold and spill materials, and emits particles and sounds.

## Base Entity

The brewing stand inherits its core physics properties from `base_item_physics2.xml`.

### Key Components:

*   **`PhysicsBody2Component`**: Defines the physical properties of the object.
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after its initial setup.
*   **`PhysicsImageShapeComponent`**: Defines the visual representation and collision shape.
    *   `image_file`: Specifies the sprite for the brewing stand (`data/props_gfx/brewing_stand.png`).
    *   `material`: Sets the base material to `wood_prop`.

## Material Inventory

This component manages the materials contained within the brewing stand.

### Key Attributes:

*   `_enabled`: Set to `1`, meaning the component is active.
*   `drop_as_item`: Set to `0`, so it doesn't drop as a collectible item when destroyed.
*   `on_death_spill`: Set to `1`, causing its contents to spill upon destruction.
*   `leak_on_damage_percent`: Set to `0.999`, meaning it will leak almost entirely when damaged.

### Material Counts:

*   **`Material material="alcohol" count="2000"`**: The brewing stand initially contains 2000 units of "alcohol" material.

## Damage Model

This component defines how the brewing stand reacts to damage and environmental effects.

### Key Attributes:

*   `air_needed`: Set to `0`, indicating it doesn't require air to function.
*   `blood_material`: Set to `alcohol`, meaning "alcohol" is spilled when it takes damage that causes bleeding.
*   `drop_items_on_death`: Set to `0`, it doesn't drop other items when destroyed.
*   `falling_damage_damage_max`, `falling_damage_damage_min`, `falling_damage_height_max`, `falling_damage_height_min`: These attributes define the damage taken from falling based on height.
*   `falling_damages`: Set to `1`, enabling falling damage.
*   `fire_damage_amount`: Set to `0.2`, defining the amount of fire damage it takes.
*   `fire_probability_of_ignition`: Set to `0`, it cannot ignite from fire.
*   `critical_damage_resistance`: Set to `1`, indicating resistance to critical damage.
*   `hp`: Set to `800`, defining its hit points.
*   `is_on_fire`: Set to `0`, it starts not on fire.
*   `materials_create_messages`: Set to `0`, it doesn't create messages when materials are applied.
*   `materials_damage`: Set to `0`, materials don't directly damage it.
*   `ragdoll_filenames_file`, `ragdoll_material`: Empty, so it doesn't create a ragdoll upon death.
*   `ui_report_damage`: Set to `0`, damage taken is not reported in the UI.

## Particle Emitters

The brewing stand has two particle emitters to create visual effects.

### Emitter 1 (Steam):

*   `emitted_material_name`: `steam`
*   `offset.x`, `offset.y`: Position relative to the entity.
*   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Variation in particle spawn position.
*   `x_vel_min/max`, `y_vel_min/max`: Velocity range for emitted particles.
*   `count_min/max`: Number of particles emitted per burst.
*   `lifetime_min/max`: Duration particles exist.
*   `create_real_particles`: Set to `1`, creates actual game particles.
*   `emit_cosmetic_particles`: Set to `0`, doesn't emit purely cosmetic particles.
*   `emission_interval_min_frames/max_frames`: Controls the timing between particle bursts.
*   `is_emitting`: Set to `1`, the emitter is active.

### Emitter 2 (Alcohol Spill):

*   `emitted_material_name`: `alcohol`
*   `offset.x`, `offset.y`: Position relative to the entity.
*   `x_pos_offset_min/max`, `y_pos_offset_min/max`: Variation in particle spawn position.
*   `x_vel_min/max`, `y_vel_min/max`: Velocity range for emitted particles (set to 0, so particles don't move initially).
*   `count_min/max`: Number of particles emitted per burst.
*   `lifetime_min/max`: Duration particles exist.
*   `create_real_particles`: Set to `1`, creates actual game particles.
*   `emit_cosmetic_particles`: Set to `0`, doesn't emit purely cosmetic particles.
*   `emission_interval_min_frames/max_frames`: Controls the timing between particle bursts (longer interval than steam).
*   `is_emitting`: Set to `1`, the emitter is active.

## Audio Loop

This component plays a looping sound effect associated with the brewing stand.

### Key Attributes:

*   `_tags`: `sound_spray`
*   `file`: `data/audio/Desktop/materials.bank`
*   `event_name`: `materials/spray`
*   `volume_autofade_speed`: `0.25`