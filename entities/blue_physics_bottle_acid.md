---
title: Blue Physics Bottle (Acid)
category: data
---

# Blue Physics Bottle (Acid)

This document details the configuration for a blue physics bottle entity in Noita, which contains and spills acid upon destruction or significant damage.

## Base Entity Configuration

The bottle inherits its core physics and visual properties from `base_item_physics2.xml`.

### `Base` Element

*   **`file`**: `data/entities/base_item_physics2.xml` - Specifies the base entity template used.

### `PhysicsBody2Component`

Controls the physical behavior of the bottle.

*   **`kill_entity_after_initialized`**: `0` - The entity does not self-destruct immediately after being created.

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape.

*   **`image_file`**: `data/props_gfx/bottle_blue.png` - The sprite used for the bottle's appearance.
*   **`material`**: `plastic_prop` - The physical material assigned for collision and interaction.

## Material Inventory

This component manages the contents of the bottle.

### `MaterialInventoryComponent`

*   **`_enabled`**: `1` - The component is active.
*   **`drop_as_item`**: `0` - The bottle does not drop as a separate item when destroyed.
*   **`on_death_spill`**: `1` - The bottle's contents will spill out when the entity dies.
*   **`leak_on_damage_percent`**: `0.999` - The bottle will leak its contents when it reaches 99.9% damage.

#### `count_per_material_type`

Specifies the materials and their quantities contained within the bottle.

*   **`Material`**:
    *   `material`: `acid` - The type of material contained.
    *   `count`: `15` - The quantity of acid.

## Damage Model

This component handles how the entity reacts to damage.

### `DamageModelComponent`

*   **`air_needed`**: `0` - No air is required for this entity's damage mechanics.
*   **`blood_material`**: `acid_gas` - The material created when the entity is damaged in a way that produces "blood" (in this case, gas).
*   **`drop_items_on_death`**: `0` - No specific items are dropped upon death, beyond its contents.
*   **`falling_damage_damage_max`**: `1.2` - Maximum damage dealt from falling.
*   **`falling_damage_damage_min`**: `0.1` - Minimum damage dealt from falling.
*   **`falling_damage_height_max`**: `250` - Maximum height from which falling damage is calculated.
*   **`falling_damage_height_min`**: `70` - Minimum height from which falling damage is calculated.
*   **`falling_damages`**: `1` - Falling damage is enabled.
*   **`fire_damage_amount`**: `0.2` - The amount of damage dealt by fire.
*   **`fire_probability_of_ignition`**: `50` - 50% chance of igniting when exposed to fire.
*   **`critical_damage_resistance`**: `1` - The entity has full resistance to critical damage.
*   **`hp`**: `0.1` - The entity has very low health, making it easily breakable.
*   **`is_on_fire`**: `0` - The entity does not start on fire.
*   **`materials_create_messages`**: `0` - No messages are created when materials interact with this entity.
*   **`materials_damage`**: `0` - Materials do not directly damage this entity.
*   **`ragdoll_filenames_file`**: `""` - No specific ragdoll files are used.
*   **`ragdoll_material`**: `""` - No specific ragdoll material is assigned.
*   **`ui_report_damage`**: `0` - Damage taken by this entity is not reported in the UI.

## Explosion on Damage

This component defines the explosive behavior when the bottle is damaged or destroyed.

### `ExplodeOnDamageComponent`

*   **`explode_on_death_percent`**: `1` - The bottle will always explode upon death.
*   **`explode_on_damage_percent`**: `0.8` - The bottle will explode when it reaches 80% damage.
*   **`physics_body_modified_death_probability`**: `0.1` - A 10% chance for the physics body to be modified upon death (potentially affecting explosion behavior).

#### `config_explosion`

Configuration for the explosion effect.

*   **`never_cache`**: `0` - The explosion can be cached.
*   **`damage`**: `1` - The base damage of the explosion.
*   **`camera_shake`**: `3` - The intensity of camera shake caused by the explosion.
*   **`explosion_radius`**: `10` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_016.xml` - The particle effect used for the explosion.
*   **`explosion_sprite_lifetime`**: `10` - The lifetime of the explosion particles.
*   **`create_cell_probability`**: `20` - 20% chance to create material cells.
*   **`create_cell_material`**: `acid` - The material of the cells created by the explosion.
*   **`hole_destroy_liquid`**: `0` - The explosion does not destroy liquids.
*   **`hole_enabled`**: `1` - The explosion can create holes in terrain.
*   **`ray_energy`**: `50000` - The energy of the explosion's damaging rays.
*   **`particle_effect`**: `1` - Particle effects are enabled for the explosion.
*   **`damage_mortals`**: `1` - The explosion damages living entities.
*   **`physics_explosion_power.min`**: `0.1` - Minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `0.2` - Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Physics objects can be thrown by the explosion.
*   **`shake_vegetation`**: `1` - Vegetation is shaken by the explosion.
*   **`sparks_count_min`**: `2` - Minimum number of sparks created.
*   **`sparks_count_max`**: `3` - Maximum number of sparks created.
*   **`sparks_enabled`**: `1` - Sparks are enabled for the explosion.
*   **`stains_enabled`**: `1` - Stains are created by the explosion.
*   **`stains_radius`**: `2` - The radius of the stains created.