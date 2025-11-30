---
title: Physics Pressure Tank
category: entities
---

# Physics Pressure Tank

This document details the configuration of the `physics_pressure_tank.xml` entity, designed to represent a breakable tank that leaks and explodes.

## Core Components

### Base Entity

The tank inherits its fundamental physics properties from `base_item_physics.xml`.

### Physics Shape

*   **`image_file`**: `data/props_gfx/pressure_tank.png` - Specifies the visual representation of the tank.
*   **`material`**: `steel` - Defines the physical material properties for collision and interaction.

### Material Inventory

This component manages the contents of the tank and its behavior when damaged or destroyed.

*   **`_enabled`**: `1` - The component is active.
*   **`drop_as_item`**: `0` - The tank does not drop as a usable item upon death.
*   **`on_death_spill`**: `1` - Contents are spilled when the tank is destroyed.
*   **`leak_on_damage_percent`**: `0.999` - The tank will start leaking when it reaches 99.9% damage.
*   **`b2_force_on_leak`**: `0.1` - A small force is applied when leaking.
*   **`kill_when_empty`**: `1` - The tank is destroyed once its contents are depleted.

#### Contents

*   **`Material material="acid" count="700"`**: The tank initially contains 700 units of acid.

### Damage Model

This component defines how the tank takes damage and its resistance.

*   **`air_needed`**: `0` - Does not require air to function or be damaged.
*   **`blood_material`**: `fire` - When damaged, it can ignite or interact with fire.
*   **`falling_damage_damage_max`**: `1.2` - Maximum damage from falling.
*   **`falling_damage_damage_min`**: `0.1` - Minimum damage from falling.
*   **`falling_damage_height_max`**: `250` - Maximum height for falling damage to apply.
*   **`falling_damage_height_min`**: `70` - Minimum height for falling damage to apply.
*   **`falling_damages`**: `0` - Falling damage is not directly applied as a damage type.
*   **`fire_damage_amount`**: `0.2` - Amount of damage taken from fire.
*   **`fire_probability_of_ignition`**: `0` - Cannot ignite from fire.
*   **`critical_damage_resistance`**: `1` - High resistance to critical damage.
*   **`hp`**: `4` - The tank has 4 hit points.

### Explode On Damage

This component governs the tank's explosive behavior.

*   **`explode_on_death_percent`**: `1` - Always explodes upon death.
*   **`explode_on_damage_percent`**: `0.1` - Can explode when taking as little as 10% damage.
*   **`physics_body_modified_death_probability`**: `0.1` - A small chance for physics to be modified upon death.

#### Explosion Configuration

*   **`never_cache`**: `0` - The explosion can be cached.
*   **`damage`**: `16` - The base damage dealt by the explosion.
*   **`camera_shake`**: `80` - Intensity of camera shake during the explosion.
*   **`explosion_radius`**: `90` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_032.xml` - Visual effect for the explosion.
*   **`explosion_sprite_lifetime`**: `10` - Duration of the explosion sprite.
*   **`create_cell_probability`**: `70` - 70% chance to create material cells.
*   **`hole_destroy_liquid`**: `0` - Does not destroy liquids.
*   **`hole_enabled`**: `1` - Creates holes in terrain.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_green_large.xml` - Entity to load for the explosion effect.
*   **`ray_energy`**: `4000000` - Energy of the explosion's damaging rays.
*   **`particle_effect`**: `1` - Enables particle effects for the explosion.
*   **`damage_mortals`**: `1` - Deals damage to living entities.
*   **`physics_explosion_power.min`**: `3.5` - Minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `4.7` - Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Physics objects are thrown by the explosion.
*   **`shake_vegetation`**: `1` - Shakes vegetation in the area.
*   **`sparks_count_min`**: `19` - Minimum number of sparks.
*   **`sparks_count_max`**: `28` - Maximum number of sparks.
*   **`sparks_enabled`**: `1` - Sparks are generated.
*   **`stains_enabled`**: `1` - Creates stains on surfaces.
*   **`stains_radius`**: `15` - Radius of the stains.
*   **`delay.min`**: `1` - Minimum delay before explosion.
*   **`delay.max`**: `4` - Maximum delay before explosion.
*   **`explosion_delay_id`**: `1` - Identifier for explosion delay.

### Audio Loop

This component plays a sound effect when the tank is active or interacting.

*   **`_tags`**: `sound_spray` - Tag associated with the sound.
*   **`file`**: `data/audio/Desktop/materials.bank` - Audio bank file.
*   **`event_name`**: `materials/spray` - Specific audio event to play.
*   **`volume_autofade_speed`**: `0.25` - Speed at which the volume fades automatically.