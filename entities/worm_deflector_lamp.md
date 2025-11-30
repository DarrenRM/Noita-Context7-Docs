---
title: Worm Deflector Lamp
category: entities
---

# Worm Deflector Lamp

This document describes the `physics_worm_deflector_lamp.xml` entity, which represents a functional lamp in Noita that repels worms.

## Core Components

The Worm Deflector Lamp is built upon several core Noita entity components, defining its physical properties, damage interactions, and unique worm-repelling behavior.

### Base Entity (`Base file="data/entities/base_item_physics.xml"`)

This establishes the fundamental physics and item-like properties of the lamp.

*   **`PhysicsBodyComponent`**:
    *   `on_death_leave_physics_body="1"`: Ensures the physics body remains after the entity is destroyed, allowing for lingering physical interactions.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/worm_deflector_lamp.png"`: Specifies the visual asset for the lamp.
    *   `material="metal_prop"`: Defines the material type, influencing its physical interactions.

### Physics Joint (`PhysicsJointComponent`)

This component attaches the lamp to its environment.

*   `nail_to_wall="1"`: The lamp is fixed to a wall or surface.
*   `breakable="1"`: The connection can be broken.
*   `pos_x="16"`, `pos_y="2"`: Local offset for the joint's attachment point.

### Damage Model (`DamageModelComponent`)

Defines how the lamp takes damage and its resistances.

*   `hp="10.2"`: The lamp's health points.
*   `falling_damage_damage_max="1.2"`, `falling_damage_damage_min="0.1"`, `falling_damage_height_max="250"`, `falling_damage_height_min="70"`: Configures damage taken from falling.
*   `fire_damage_amount="0.4"`: Amount of damage taken from fire.
*   `materials_that_damage="fire,lava,acid"`: Lists materials that can damage the lamp.
*   `materials_how_much_damage="0.0002,0.0001,0.001"`: Specifies the damage multiplier for each material in `materials_that_damage`.
*   `critical_damage_resistance="1"`: High resistance to critical damage.
*   **`damage_multipliers`**:
    *   `melee="0.1"`: Reduced damage taken from melee attacks.

### Explosion on Damage (`ExplodeOnDamageComponent`)

Determines the lamp's behavior when damaged to the point of destruction.

*   `explode_on_death_percent="1"`: The entity will explode when its health reaches 0.
*   `physics_body_modified_death_probability="0.9"`: If the physics body is sufficiently modified upon death, there's a 90% chance of an explosion.
*   `physics_body_destruction_required="0.3"`: The physics body needs to be at least 30% destroyed for the death explosion probability to apply.
*   **`config_explosion`**:
    *   `camera_shake="40"`: Intensity of camera shake during the explosion.
    *   `explosion_radius="20"`: The radius of the explosion's effect.
    *   `load_this_entity="data/entities/particles/particle_explosion/main.xml"`: The particle effect to spawn upon explosion.
    *   `ray_energy="30000"`: Energy of the explosion's damaging rays.
    *   `physics_explosion_power.min="1.9"`, `physics_explosion_power.max="2.5"`: The force of the physics-based explosion.
    *   `sparks_count_min="10"`, `sparks_count_max="25"`: Number of sparks generated.
    *   `stains_enabled="1"`, `stains_radius="15"`: Enables and defines the radius of stains left by the explosion.

### Visual and Light Effects (`Entity` with `ParticleEmitterComponent` and `LightComponent`)

This nested entity creates visual flair and the lamp's illumination.

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_blue"`: Spawns blue sparks.
    *   `lifetime_min="1"`, `lifetime_max="3"`: Duration of emitted sparks.
    *   `x_vel_min="-5"`, `x_vel_max="5"`, `y_vel_min="-20"`, `y_vel_max="5"`: Velocity range for sparks.
    *   `count_min="15"`, `count_max="15"`: Number of sparks emitted per interval.
    *   `emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`: How often sparks are emitted.
    *   `area_circle_radius.max="11"`: The radius of the emission area.
    *   `is_emitting="1"`: The emitter is active.
*   **`LightComponent`**:
    *   `radius="80"`: The radius of the light emitted by the lamp.
    *   `r="45"`, `g="165"`, `b="250"`: The RGB color of the light (a cool blue).

### Worm Repulsion (`WormAttractorComponent`)

This is the core component responsible for the lamp's primary function.

*   `direction="-1"`: Indicates the direction of repulsion (away from the lamp).
*   `radius="1024"`: The maximum distance at which the lamp affects worms.

### UI Information (`UIInfoComponent`)

Provides the name displayed in the game's UI.

*   `name="$building_worm_deflector"`: The in-game name of the building.