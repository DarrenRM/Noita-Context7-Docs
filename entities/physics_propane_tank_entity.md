---
title: Physics Propane Tank Entity
category: entities
---

# Physics Propane Tank Entity

This document details the `physics_propane_tank.xml` entity, which represents a propane tank that can be interacted with physically and explode.

## Key Components and Attributes

The propane tank entity is built upon several core components that define its behavior and properties.

### Base Entity (`Base`)

This component inherits functionality from `base_item_physics2.xml`, providing fundamental physics and item properties.

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized`: Set to `0`, meaning the entity persists after its initial setup.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: Specifies the visual representation of the propane tank (`data/props_gfx/propane_tank.png`).
    *   `material`: Defines the physical material as `steel`.

### Material Inventory (`MaterialInventoryComponent`)

This component manages the internal materials of the tank and how they behave when damaged or depleted.

*   `drop_as_item`: Set to `0`, so it doesn't drop as a usable item upon death.
*   `on_death_spill`: Set to `1`, causing its contents to spill when destroyed.
*   `leak_on_damage_percent`: Set to `0.999`, meaning it will start leaking when almost completely damaged.
*   `b2_force_on_leak`: `0.6` - The force applied when leaking.
*   `kill_when_empty`: Set to `1`, the entity is destroyed once its internal material is depleted.
*   **`count_per_material_type`**: Defines the initial contents.
    *   `Material material="blood_cold_vapour" count="300"`: The tank initially contains 300 units of `blood_cold_vapour`.

### Damage Model (`DamageModelComponent`)

This component governs how the entity takes damage and reacts to it.

*   `air_needed`: `0` - Does not require air to function or take damage.
*   `blood_material`: `blood_cold_vapour` - The material associated with its "blood" or internal substance.
*   `falling_damage_damage_max`: `1.2` - Maximum damage from falling.
*   `falling_damage_damage_min`: `0.1` - Minimum damage from falling.
*   `falling_damage_height_max`: `250` - Maximum height for falling damage to apply.
*   `falling_damage_height_min`: `70` - Minimum height for falling damage to apply.
*   `fire_damage_amount`: `0.2` - The amount of damage taken from fire.
*   `hp`: `2` - The entity's hit points.
*   `critical_damage_resistance`: `1` - High resistance to critical damage.

### Explosion on Damage (`ExplodeOnDamageComponent`)

This component defines the explosion behavior when the entity is damaged or destroyed.

*   `explode_on_death_percent`: `1.0` - Guarantees an explosion upon death.
*   `explode_on_damage_percent`: `0.0` - The explosion is triggered by damage, not just death.
*   `physics_body_modified_death_probability`: `1.0` - High probability of explosion if physics body is modified upon death.
*   `physics_body_destruction_required`: `0.3` - Requires 30% destruction of the physics body to trigger explosion.
*   **`config_explosion`**: Detailed configuration for the explosion effect.
    *   `damage`: `13` - The base damage dealt by the explosion.
    *   `camera_shake`: `60` - The intensity of camera shake.
    *   `explosion_radius`: `60` - The radius of the explosion.
    *   `explosion_sprite`: `data/particles/explosion_032.xml` - Visual effect for the explosion.
    *   `create_cell_probability`: `40` - Chance to create material cells.
    *   `create_cell_material`: `blood_cold_vapour` - The material of the created cells.
    *   `hole_enabled`: `1` - Creates a hole in the environment.
    *   `ray_energy`: `2000000` - Energy of the explosion's rays.
    *   `particle_effect`: `1` - Enables particle effects.
    *   `damage_mortals`: `1` - The explosion damages living entities.
    *   `physics_explosion_power.min`: `2.5` - Minimum physics force applied by the explosion.
    *   `physics_explosion_power.max`: `3.5` - Maximum physics force applied by the explosion.
    *   `sparks_count_min`: `15` - Minimum number of sparks.
    *   `sparks_count_max`: `20` - Maximum number of sparks.
    *   `spark_material`: `plasma_fading` - The material of the sparks.
    *   `stains_enabled`: `1` - Creates stains on surfaces.
    *   `stains_radius`: `15` - The radius of the stains.
    *   `delay.min`: `1` - Minimum delay before explosion.
    *   `delay.max`: `4` - Maximum delay before explosion.
    *   `audio_event_name`: `explosions/propane_tank` - The sound event triggered by the explosion.

### Audio Loop (`AudioLoopComponent`)

This component is used for sound effects, though its specific application here (`sound_spray`) might be a remnant or intended for a specific interaction not fully detailed in this XML.

*   `file`: `data/audio/Desktop/materials.bank` - The audio bank file.
*   `event_name`: `materials/spray` - The audio event name.