---
title: Greed Crystal Entity
category: entities
---

# Greed Crystal Entity

This document details the `greed_crystal.xml` entity, which represents a destructible crystal that explodes when damaged.

## Core Components

### Base Entity (`Base file="data/entities/base_item_physics.xml"`)

This component provides the fundamental physics properties for the Greed Crystal.

*   **`PhysicsBodyComponent`**:
    *   `on_death_leave_physics_body="1"`: Ensures the physics body remains after the entity is destroyed, allowing for lingering physical interactions.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/worm_deflector_crystal.png"`: Specifies the visual sprite for the crystal.
    *   `material="magic_crystal_green"`: Defines the material properties, influencing interactions with other game elements.

### Damage (`DamageModelComponent`)

Manages how the Greed Crystal takes damage and its reactions.

*   **`hp="10.2"`**: The health points of the crystal.
*   **`falling_damages="0"`**: The crystal does not take damage from falling.
*   **`fire_damage_amount="0.4"`**: The amount of damage taken from fire.
*   **`materials_damage="1"`**: Enables damage from contact with specific materials.
*   **`materials_that_damage="fire,lava,acid"`**: Lists materials that will damage the crystal.
*   **`materials_how_much_damage="0.0002,0.0001,0.001"`**: The damage multiplier for each material listed above.
*   **`damage_multipliers`**:
    *   `melee="0.1"`: Reduces damage taken from melee attacks.

### Explosion (`ExplodeOnDamageComponent`)

Defines the behavior when the crystal is destroyed, specifically its explosion.

*   **`explode_on_death_percent="1"`**: The crystal will always explode upon death.
*   **`physics_body_modified_death_probability="0.9"`**: A high probability that the physics body will be modified upon death (likely contributing to the explosion force).
*   **`physics_body_destruction_required="0.3"`**: A portion of the physics body needs to be destroyed before the explosion is triggered.
*   **`config_explosion`**:
    *   `camera_shake="40"`: The intensity of camera shake upon explosion.
    *   `explosion_radius="20"`: The area of effect for the explosion.
    *   `load_this_entity="data/entities/particles/particle_explosion/main_green.xml"`: The particle effect to spawn upon explosion.
    *   `ray_energy="30000"`: The energy of the explosion's damaging rays.
    *   `physics_explosion_power.min="1.9"`, `physics_explosion_power.max="2.5"`: The minimum and maximum force of the physics-based explosion.
    *   `sparks_count_min="10"`, `sparks_count_max="25"`: The range for the number of sparks created.
    *   `stains_radius="15"`: The radius of stains left by the explosion.

## Visual and Effect Components

### Particle Emitter (`ParticleEmitterComponent`)

Responsible for emitting visual particles.

*   **`emitted_material_name="spark_green"`**: The material of the particles emitted.
*   **`lifetime_min="1"`, `lifetime_max="3"`**: The duration particles exist.
*   **`x_vel_min="-5"`, `x_vel_max="5"`**: Horizontal velocity range of particles.
*   **`y_vel_min="-20"`, `y_vel_max="5"`**: Vertical velocity range of particles.
*   **`count_min="15"`, `count_max="15"`**: The number of particles emitted per burst.
*   **`emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`**: The frame interval between particle emissions.
*   **`area_circle_radius.max="11"`**: The radius of the area from which particles are emitted.

### Light Component (`LightComponent`)

Adds a light source to the entity.

*   **`radius="80"`**: The radius of the light.
*   **`r="45"`, `g="250"`, `b="165"`**: The RGB color of the light (a greenish-yellow).

## Metadata and Scripting

### UI Information (`UIInfoComponent`)

Provides information for the game's user interface.

*   **`name="$item_greed_crystal"`**: The internal name used for localization and referencing the item.

### Lua Scripting (`LuaComponent`)

Attaches custom Lua scripting to the entity.

*   **`script_death="data/scripts/magic/greed_curse/greed_crystal_death.lua"`**: The script executed when the entity dies, likely handling the specific logic for the Greed Curse.
*   **`remove_after_executed="0"`**: The script will not be removed after execution.