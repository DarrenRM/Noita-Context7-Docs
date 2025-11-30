---
title: Physics Trap - Ignite
category: entities
---

# Physics Trap - Ignite

This entity represents a physics-based trap that ignites and explodes when triggered by electricity. It's designed to be a hazard in the environment, reacting to external stimuli.

## Key Components

### Base Entity and Physics

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics properties for interactive objects.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/trap_ignite_a.png"`: Defines the visual appearance of the trap.
    *   `material="steel"`: Sets the physical material properties.

### Electrical Triggering

*   **`ElectricityReceiverComponent`**:
    *   `radius="6"`: The area around the trap that can receive electrical signals.
    *   `active_time_frames="100"`: How long the trap remains active after receiving a signal.
*   **`LuaComponent script_electricity_receiver_switched="data/scripts/props/physics_trap.lua"`**: Links the electrical receiver to a script that handles its behavior when switched on.

### Variable Storage for Activation

These components define which effects are enabled when the trap is activated by electricity.

*   **`VariableStorageComponent name="enable_component" value_string="electricity_effect"`**: Enables the electrical effect component.
*   **`VariableStorageComponent name="enable_component" value_string="particles_a"`**: Enables the first particle emitter.
*   **`VariableStorageComponent name="enable_component" value_string="particles_b"`**: Enables the second particle emitter.
*   **`VariableStorageComponent name="enable_component" value_string="particles_c"`**: Enables the sprite particle emitter.

### Scripted Ignition Effect

*   **`LuaComponent _tags="electricity_effect" _enabled="0" script_source_file="data/scripts/props/physics_trap_ignite.lua" execute_every_n_frame="160"`**: This component executes a Lua script (`physics_trap_ignite.lua`) that handles the ignition and particle effects. It's initially disabled and triggered by the `electricity_effect` tag. `execute_every_n_frame="160"` dictates the timing of its script execution.

### Particle Emitters

These components generate visual effects upon activation.

*   **`ParticleEmitterComponent _tags="particles_a" _enabled="0"`**:
    *   `emitted_material_name="fire"`: Emits fire particles.
    *   `create_real_particles="1"`: Creates actual physics particles.
    *   `lifetime_min="15"`, `lifetime_max="35"`: Duration of individual fire particles.
    *   `count_min="100"`, `count_max="100"`: Number of particles emitted.
    *   `area_circle_radius.min="12"`, `area_circle_radius.max="12"`: The radius of the emission area.
    *   `emission_interval_min_frames="160"`, `emission_interval_max_frames="160"`: Controls how often particles are emitted.
*   **`ParticleEmitterComponent _tags="particles_b" _enabled="0"`**:
    *   `emitted_material_name="alcohol_gas"`: Emits alcohol gas particles.
    *   `count_min="500"`, `count_max="500"`: A larger quantity of gas particles.
    *   `area_circle_radius.min="10"`, `area_circle_radius.max="25"`: A wider emission area for gas.
*   **`SpriteParticleEmitterComponent _tags="particles_c" _enabled="0"`**:
    *   `sprite_file="data/particles/explosion_032.xml"`: Uses a specific sprite for a visual explosion effect.
    *   `count_min="1"`, `count_max="1"`: Emits a single explosion sprite.

### Damage and Destruction

*   **`DamageModelComponent`**: Defines how the trap takes damage and its properties.
    *   `hp="30"`: Hit points of the trap.
    *   `materials_that_damage="fire,lava,acid"`: Materials that can damage the trap.
    *   `materials_how_much_damage="0.0002,0.0001,0.001"`: The amount of damage from each material.
    *   `falling_damages="0"`: The trap does not take damage from falling.
    *   `fire_damage_amount="0.4"`: The amount of fire damage it inflicts.
*   **`ExplodeOnDamageComponent`**: Manages the explosion behavior.
    *   `explode_on_death_percent="1"`: The trap will explode when its HP reaches 0.
    *   `physics_body_destruction_required="0.15"`: The trap's physics body needs to be at least 15% destroyed for a potential explosion.
    *   `physics_body_modified_death_probability="0.9"`: If the destruction threshold is met upon death, there's a 90% chance it will explode.
    *   **`config_explosion`**: Details of the explosion:
        *   `damage="2.6"`: The damage dealt by the explosion.
        *   `camera_shake="10"`: The intensity of camera shake.
        *   `explosion_radius="32"`: The radius of the explosion.
        *   `load_this_entity="data/entities/projectiles/deck/mist_alcohol.xml"`: Spawns an entity (alcohol mist) upon explosion.
        *   `ray_energy="75000"`: The energy of the explosion's damaging rays.
        *   `physics_explosion_power.min="1.7"`, `physics_explosion_power.max="2.3"`: The force of the physics-based explosion.
        *   `audio_event_name="explosions/machine_small"`: The sound effect played during the explosion.