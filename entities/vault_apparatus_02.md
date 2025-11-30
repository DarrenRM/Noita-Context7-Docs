---
title: Vault Apparatus 02
category: entities
---

# Vault Apparatus 02

This entity represents a "Vault Apparatus 02", a prop that can be damaged and explode. It's primarily composed of steel and contains a significant amount of cold blood vapor.

## Key Components

### Base Entity

*   **`mortal` tag**: Essential for the entity to be able to explode.
*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits physics properties for interaction with the game world.
    *   **`PhysicsBodyComponent`**:
        *   `is_static="1"`: The apparatus is initially stationary.
        *   `on_death_leave_physics_body="0"`: The physics body is removed upon death (explosion).
    *   **`PhysicsImageShapeComponent`**:
        *   `image_file="data/props_gfx/vault_apparatus_02.png"`: Specifies the visual sprite for the apparatus.
        *   `material="steel"`: The primary material of the apparatus.

### Material Inventory

*   **`MaterialInventoryComponent`**: Manages the materials contained within the apparatus.
    *   `drop_as_item="0"`: The apparatus does not drop as a usable item upon destruction.
    *   `on_death_spill="1"`: Spills its contents when destroyed.
    *   `leak_pressure_min="0.5"`, `leak_pressure_max="0.8"`: Defines the pressure range for material leakage.
    *   `leak_on_damage_percent="0.5"`: Starts leaking when 50% damaged.
    *   **`count_per_material_type`**:
        *   `Material material="blood_cold" count="1000"`: Contains 1000 units of cold blood.

### Damage Model

*   **`DamageModelComponent`**: Defines how the apparatus takes damage and reacts.
    *   `hp="50"`: Has 50 hit points.
    *   `materials_damage="lava,acid"`: Can be damaged by lava and acid.
    *   `materials_how_much_damage="0.0002,0.0001,0.001"`: Specifies damage values for different materials.
    *   `critical_damage_resistance="1"`: Highly resistant to critical damage.
    *   `falling_damages="0"`: Does not take damage from falling.
    *   **`damage_multipliers`**:
        *   `melee="0.1"`: Takes only 10% damage from melee attacks.

### Explosion Component

*   **`ExplodeOnDamageComponent`**: Handles the explosion behavior.
    *   `explode_on_death_percent="1"`: Explodes when its HP reaches 0.
    *   `physics_body_modified_death_probability="0.9"`: Has a 90% chance to explode if its physics body is sufficiently modified upon death.
    *   `physics_body_destruction_required="0.1"`: Requires 10% of its physics body to be destroyed before triggering the explosion probability.
    *   **`config_explosion`**: Defines the properties of the explosion.
        *   `damage="13"`: Deals 13 damage to nearby entities.
        *   `camera_shake="60"`: Causes significant camera shake.
        *   `explosion_radius="60"`: The explosion affects an area of radius 60.
        *   `explosion_sprite="data/particles/explosion_032.xml"`: Uses a specific sprite for the explosion visual.
        *   `create_cell_material="blood_cold_vapour"`: Creates cold blood vapor cells upon explosion.
        *   `load_this_entity="data/entities/particles/particle_explosion/main_bluesmoke.xml"`: Loads a blue smoke particle effect.
        *   `ray_energy="2000000"`: High energy for raycasting effects.
        *   `physics_explosion_power.min="2.5"`, `physics_explosion_power.max="3.5"`: Defines the force of the physics-based explosion.
        *   `sparks_count_min="15"`, `sparks_count_max="20"`: Generates a number of sparks.
        *   `spark_material="plasma_fading"`: Sparks are made of fading plasma.
        *   `delay.min="1"`, `delay.max="4"`: The explosion has a random delay between 1 and 4 frames.

### Particle Emitters

*   **`ParticleEmitterComponent`**:
    *   Emits `blood_cold_vapour` particles.
    *   `count_min="10"`, `count_max="50"`: Emits between 10 and 50 particles per emission.
    *   `create_real_particles="1"`: Creates actual game particles.
    *   `emission_interval_min_frames="80"`, `emission_interval_max_frames="80"`: Emits particles every 80 frames.
    *   `is_emitting="1"`: The emitter is active.

### Audio Components

*   **`AudioLoopComponent`**:
    *   Plays a looping sound associated with spraying materials.
    *   `event_name="materials/spray"`: Specific audio event.
*   **`AudioComponent`**:
    *   Plays a "collision/metalhollow" sound event upon interaction.