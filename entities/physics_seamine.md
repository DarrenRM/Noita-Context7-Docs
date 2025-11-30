---
title: Physics Seamine
category: entities
---

# Physics Seamine

This document details the configuration of the "Physics Seamine" entity in Noita, focusing on its properties relevant to AI-assisted modding.

## Overview

The Physics Seamine is a physics-enabled prop that functions as a proximity explosive. It is designed to detonate when damaged or when its physics body is sufficiently modified.

## Key Components and Attributes

### Base Entity

The seamine inherits its core physics and visual properties from `base_item_physics2.xml`.

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after initialization.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual asset for the seamine (`data/props_gfx/seamine.png`).
    *   `material`: Sets the base material to `metal_rust`.

### Material Inventory

This component defines what materials the seamine spills upon death and how it leaks.

*   **`MaterialInventoryComponent`**:
    *   `drop_as_item`: Set to `0`, indicating it does not drop as a collectible item.
    *   `on_death_spill`: Set to `1`, meaning it spills its contents when destroyed.
    *   `leak_on_damage_percent`: Set to `0.5`, causing it to leak when at 50% damage.
    *   **`count_per_material_type`**:
        *   `Material material="liquid_fire" count="300"`: Contains 300 units of `liquid_fire`.

### Damage Model

This component governs how the seamine reacts to damage and environmental effects.

*   **`DamageModelComponent`**:
    *   `air_needed`: Set to `0`, it does not require air.
    *   `blood_material`: Set to `oil`, influencing its behavior when damaged.
    *   `falling_damage_damage_max`, `falling_damage_damage_min`, `falling_damage_height_max`, `falling_damage_height_min`, `falling_damages`: These attributes are configured but `falling_damages` is `0`, meaning it doesn't take damage from falling.
    *   `fire_damage_amount`: `0.4`.
    *   `fire_probability_of_ignition`: `0`, it cannot ignite from fire.
    *   `critical_damage_resistance`: `1`, indicating high resistance to critical damage.
    *   `hp`: `0.3`, a very low health value.
    *   `materials_damage`: `1`, it takes damage from certain materials.
    *   `materials_that_damage`: `fire,lava,acid`.
    *   `materials_how_much_damage`: `0.0002,0.0001,0.001`, defining the damage taken from the listed materials.
    *   **`damage_multipliers`**:
        *   `melee`: `0.1`, significantly reduces melee damage.

### Explosion Component

This component defines the seamine's explosive behavior.

*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: Set to `1`, it will always explode upon death.
    *   `explode_on_damage_percent`: Set to `0.0`, it does not explode solely based on a percentage of damage taken.
    *   `physics_body_modified_death_probability`: `0.8`, a high chance of exploding if its physics body is modified upon death.
    *   `physics_body_destruction_required`: `0.25`, requires 25% of its physics body to be destroyed before triggering the `physics_body_modified_death_probability`.
    *   **`config_explosion`**:
        *   `damage`: `2.8`, the base damage of the explosion.
        *   `camera_shake`: `40`, intensity of camera shake.
        *   `explosion_radius`: `50`, the area of effect.
        *   `explosion_sprite`: `data/particles/explosion_032.xml`, visual effect of the explosion.
        *   `load_this_entity`: `data/entities/particles/particle_explosion/main_gunpowder_large.xml`, loads a specific explosion particle entity.
        *   `ray_energy`: `700000`, energy of the explosion's rays.
        *   `physics_explosion_power.min`, `physics_explosion_power.max`: `1.9` to `2.5`, the force of the physics-based explosion.
        *   `sparks_enabled`: `1`, sparks are generated.
        *   `stains_enabled`: `1`, stains are left behind.
        *   `delay.min`, `delay.max`: `1` to `4`, the explosion has a variable delay.

### Audio Component

*   **`AudioLoopComponent`**:
    *   `_tags`: `sound_spray`, indicating it's associated with spray sounds.
    *   `file`: `data/audio/Desktop/materials.bank`.
    *   `event_name`: `materials/spray`.

### Physics Body Collision Damage

*   **`PhysicsBodyCollisionDamageComponent`**:
    *   `_tags`: `enabled_in_world`, active when in the game world.
    *   `speed_threshold`: `150.0`, triggers damage when colliding at this speed or higher.