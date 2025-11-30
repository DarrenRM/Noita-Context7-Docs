---
title: Worm Deflector Crystal
category: entities
---

# Worm Deflector Crystal

This entity defines a Worm Deflector Crystal, a building that repels worms. It's designed to explode when damaged or destroyed, creating a significant physics-based explosion and emitting blue sparks and light.

## Key Components

### Base Entity (`Base file="data/entities/base_item_physics.xml"`)

This component establishes the fundamental physics properties of the crystal.

*   **`PhysicsBodyComponent`**:
    *   `on_death_leave_physics_body="1"`: Ensures the physics body remains after the entity is destroyed, allowing for continued interaction with the physics engine.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/worm_deflector_crystal.png"`: Specifies the visual sprite for the crystal.
    *   `material="magic_crystal"`: Defines the material properties, influencing interactions with other physics objects.

### Damage (`DamageModelComponent`)

Manages how the crystal takes damage and its reactions.

*   **`hp="10.2"`**: The hit points of the crystal.
*   **`falling_damage_damage_max="1.2"`, `falling_damage_damage_min="0.1"`, `falling_damage_height_max="250"`, `falling_damage_height_min="70"`**: Defines parameters for damage taken from falling.
*   **`fire_damage_amount="0.4"`**: The amount of damage taken from fire.
*   **`materials_that_damage="fire,lava,acid"`**: Lists materials that will damage the crystal.
*   **`materials_how_much_damage="0.0002,0.0001,0.001"`**: The corresponding damage values for each material listed above.
*   **`critical_damage_resistance="1"`**: Indicates resistance to critical damage.
*   **`damage_multipliers`**:
    *   `melee="0.1"`: Reduces damage taken from melee attacks.

### Explosion (`ExplodeOnDamageComponent`)

Controls the explosion behavior when the crystal is damaged or destroyed.

*   **`explode_on_death_percent="1"`**: Guarantees an explosion upon death.
*   **`physics_body_modified_death_probability="0.9"`**: If the physics body is sufficiently modified (see `physics_body_destruction_required`), there's a 90% chance of an explosion.
*   **`physics_body_destruction_required="0.3"`**: The threshold (0.0 to 1.0) of physics body destruction needed to trigger the `physics_body_modified_death_probability`.
*   **`config_explosion`**:
    *   `camera_shake="40"`: The intensity of camera shake during the explosion.
    *   `explosion_radius="20"`: The radius of the explosion's effect.
    *   `load_this_entity="data/entities/particles/particle_explosion/main_bluesmoke.xml"`: The entity to load for the explosion's visual effects.
    *   `ray_energy="30000"`: The energy of the explosion's rays.
    *   `physics_explosion_power.min="1.9"`, `physics_explosion_power.max="2.5"`: The minimum and maximum force of the physics explosion.
    *   `sparks_count_min="10"`, `sparks_count_max="25"`: The range for the number of sparks generated.
    *   `stains_radius="15"`: The radius of stains left by the explosion.

### Visuals and Effects (`Entity` block within `ExplodeOnDamageComponent`)

This nested entity handles visual effects like sparks and light.

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_blue"`: The type of particle emitted.
    *   `lifetime_min="1"`, `lifetime_max="3"`: The duration particles exist.
    *   `x_vel_min="-5"`, `x_vel_max="5"`, `y_vel_min="-20"`, `y_vel_max="5"`: Velocity parameters for emitted particles.
    *   `count_min="15"`, `count_max="15"`: The number of particles emitted per burst.
    *   `emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`: The frame interval between particle emissions.
    *   `area_circle_radius.max="11"`: The maximum radius of the emission area.
*   **`LightComponent`**:
    *   `radius="80"`: The radius of the light emitted.
    *   `r="45"`, `g="165"`, `b="250"`: The RGB color of the light (a bright blue).

### Behavior (`WormAttractorComponent`)

This component is responsible for the crystal's primary function of repelling worms.

*   **`direction="-1"`**: Indicates the direction of attraction/repulsion (likely away from the crystal).
*   **`radius="750"`**: The effective range within which worms are affected.

### Identification (`UIInfoComponent`)

Provides information for the game's user interface.

*   **`name="$building_worm_deflector"`**: The internal name used for localization and identification.

### Scripting (`LuaComponent`)

Attaches a Lua script for custom behavior.

*   **`script_death="data/scripts/buildings/worm_deflector_death.lua"`**: The script executed when the entity dies.
*   **`remove_after_executed="0"`**: The script will not be removed after execution.