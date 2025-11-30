---
title: Green Physics Bottle
category: entities
---

# Green Physics Bottle

This document details the configuration of the `physics_bottle_green.xml` entity, a prop in Noita that simulates a breakable green bottle filled with alcohol.

## Base Entity Configuration

The bottle inherits its core physics and visual properties from `base_item_physics2.xml`.

### `PhysicsBody2Component`

This component defines the physical behavior of the bottle.

*   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after its initial setup.

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape of the bottle.

*   `image_file`: Specifies the sprite used for the bottle: `data/props_gfx/bottle_green.png`.
*   `material`: The physical material assigned to the bottle's collision shape: `plastic_prop`.

## Material Inventory

The `MaterialInventoryComponent` manages the contents of the bottle.

### `MaterialInventoryComponent`

*   `_enabled`: Set to `1`, meaning this component is active.
*   `drop_as_item`: Set to `0`, indicating the contents do not drop as a separate item upon destruction.
*   `on_death_spill`: Set to `1`, meaning the bottle's contents will spill when it is destroyed.
*   `leak_on_damage_percent`: Set to `0.999`, meaning the bottle will leak its contents when it reaches 99.9% damage.

#### `count_per_material_type`

This table defines the materials and their quantities contained within the bottle.

| Material | Count |
| :------- | :---- |
| `alcohol` | `20` |

## Damage and Destruction

The `DamageModelComponent` and `ExplodeOnDamageComponent` define how the bottle reacts to damage and destruction.

### `DamageModelComponent`

This component governs how the bottle takes damage and its associated effects.

*   `air_needed`: Set to `0`, indicating no air is required for its damage mechanics.
*   `blood_material`: Set to `alcohol`, implying that alcohol is the primary fluid associated with its damage or destruction effects.
*   `drop_items_on_death`: Set to `0`, meaning no specific items are dropped upon death.
*   `falling_damage_damage_max`: Maximum damage from falling: `1.2`.
*   `falling_damage_damage_min`: Minimum damage from falling: `0.1`.
*   `falling_damage_height_max`: Maximum height for falling damage to apply: `250`.
*   `falling_damage_height_min`: Minimum height for falling damage to apply: `70`.
*   `falling_damages`: Set to `1`, enabling falling damage.
*   `fire_damage_amount`: Amount of damage from fire: `0.2`.
*   `fire_probability_of_ignition`: Probability of igniting from fire: `50`.
*   `critical_damage_resistance`: Set to `1`, indicating resistance to critical damage.
*   `hp`: Hit points of the bottle: `0.1`.
*   `is_on_fire`: Set to `0`, the bottle is not initially on fire.
*   `materials_create_messages`: Set to `0`, no messages are created when materials interact.
*   `materials_damage`: Set to `0`, materials do not directly damage the bottle.
*   `ragdoll_filenames_file`: Empty, no ragdoll files are used.
*   `ragdoll_material`: Empty, no ragdoll material is specified.
*   `ui_report_damage`: Set to `0`, damage is not reported in the UI.

### `ExplodeOnDamageComponent`

This component defines the explosion behavior when the bottle is damaged or destroyed.

*   `explode_on_death_percent`: Set to `1`, the bottle explodes upon death.
*   `explode_on_damage_percent`: Set to `0.8`, the bottle explodes when it reaches 80% damage.
*   `physics_body_modified_death_probability`: Probability of physics body modification on death: `0.1`.

#### `config_explosion`

This sub-component configures the details of the explosion.

*   `never_cache`: Set to `0`, the explosion can be cached.
*   `damage`: Base damage of the explosion: `1`.
*   `camera_shake`: Camera shake intensity: `2`.
*   `explosion_radius`: Radius of the explosion: `7`.
*   `explosion_sprite`: Particle effect used for the explosion: `data/particles/explosion_008.xml`.
*   `explosion_sprite_lifetime`: Lifetime of the explosion sprite: `10`.
*   `create_cell_probability`: Probability of creating cells: `50`.
*   `create_cell_material`: Material of the created cells: `spark`.
*   `hole_destroy_liquid`: Set to `0`, does not destroy liquids.
*   `hole_enabled`: Set to `1`, creates holes.
*   `ray_energy`: Energy of the explosion's rays: `50000`.
*   `particle_effect`: Set to `1`, enables particle effects.
*   `damage_mortals`: Set to `1`, deals damage to mortals.
*   `physics_explosion_power.min`: Minimum physics explosion force: `0.05`.
*   `physics_explosion_power.max`: Maximum physics explosion force: `0.17`.
*   `physics_throw_enabled`: Set to `1`, enables physics-based throwing of debris.
*   `sparks_count_max`: Maximum number of sparks: `2`.
*   `sparks_count_min`: Minimum number of sparks: `1`.
*   `sparks_enabled`: Set to `1`, enables sparks.
*   `stains_enabled`: Set to `1`, enables stains.
*   `stains_radius`: Radius of the stains: `2`.