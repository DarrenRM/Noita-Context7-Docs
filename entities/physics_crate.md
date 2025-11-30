---
title: Physics Crate
category: entities
---

# Physics Crate

This document details the configuration of a physics-enabled crate entity in Noita, designed to interact with the game's physics and damage systems.

## Core Components

The crate is built upon several key components that define its behavior and properties.

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits fundamental physics properties from a base physics item.

### Physics Shape and Body

*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/crate.png"`: Specifies the visual sprite for the crate.
    *   `material="wood_prop"`: Defines the physical material properties.
*   **`PhysicsBodyComponent`**:
    *   `on_death_leave_physics_body="1"`: Ensures the physics body remains after the entity is destroyed.

### Material Inventory

*   **`MaterialInventoryComponent`**: Manages the materials contained within the crate.
    *   `_enabled="1"`: The component is active.
    *   `drop_as_item="0"`: The crate does not drop its contents as a single item upon death.
    *   `on_death_spill="1"`: Contents are spilled when the crate is destroyed.
    *   `leak_on_damage_percent="0.999"`: A very high percentage of damage is required to start leaking.
    *   **`count_per_material_type`**: Defines the materials and their quantities inside.
        *   `Material material="liquid_fire" count="100"`: Contains 100 units of liquid fire.

### Damage Model

*   **`DamageModelComponent`**: Governs how the crate reacts to damage.
    *   `hp="2"`: The crate has 2 hit points.
    *   `falling_damage_damage_max="1.2"`: Maximum damage from falling.
    *   `falling_damage_damage_min="0.1"`: Minimum damage from falling.
    *   `falling_damage_height_max="250"`: Maximum height for falling damage to apply.
    *   `falling_damage_height_min="70"`: Minimum height for falling damage to apply.
    *   `fire_damage_amount="0.2"`: Amount of damage taken from fire.
    *   `critical_damage_resistance="1"`: No resistance to critical damage.
    *   **`damage_multipliers`**: Modifiers for different damage types.
        *   `melee="0.1"`: Takes 10% of normal damage from melee attacks.

### Explosion on Damage

*   **`ExplodeOnDamageComponent`**: Enables the crate to explode under certain conditions.
    *   `explode_on_death_percent="1"`: Always explodes upon death.
    *   `explode_on_damage_percent="0.1"`: Has a 10% chance to explode when taking damage.
    *   `physics_body_modified_death_probability="0.4"`: A 40% chance for the physics body to be modified upon death (likely related to explosion force).
    *   **`config_explosion`**: Configuration for the explosion effect.
        *   `damage="3"`: The explosion deals 3 damage.
        *   `camera_shake="40"`: The camera shakes significantly.
        *   `explosion_radius="45"`: The explosion affects an area of 45 units.
        *   `explosion_sprite="data/particles/explosion_032.xml"`: Visual effect for the explosion.
        *   `create_cell_material="fire"`: Creates fire cells upon explosion.
        *   `hole_enabled="1"`: Creates holes in the environment.
        *   `ray_energy="500000"`: High energy for destructive rays.
        *   `damage_mortals="1"`: The explosion damages living entities.
        *   `physics_explosion_power.min="1.8"`: Minimum physics force applied by the explosion.
        *   `physics_explosion_power.max="2.5"`: Maximum physics force applied by the explosion.
        *   `sparks_enabled="1"`: Generates sparks.
        *   `stains_enabled="1"`: Leaves stains on surfaces.
        *   `delay.min="1"`: Minimum delay before explosion.
        *   `delay.max="4"`: Maximum delay before explosion.