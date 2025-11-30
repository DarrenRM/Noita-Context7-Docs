---
title: Physics Trap - Electricity
category: entities
---

---

# Physics Trap - Electricity

This entity represents a physics-based trap that is activated by electricity. When powered, it can emit electrical particles and trigger an explosion.

## Key Components

### Base Entity
- **`Base file="data/entities/base_item_physics.xml"`**: Inherits fundamental physics properties for interactive objects.
- **`PhysicsImageShapeComponent`**:
    - `image_file`: `data/props_gfx/trap_electricity.png` - Defines the visual appearance of the trap.
    - `material`: `steel` - Sets the physical material for collision and interaction.

### Electricity Receiver
- **`ElectricityReceiverComponent`**:
    - `radius`: `6` - The area around the trap that can receive an electrical signal.
    - `active_time_frames`: `100` - How long the trap remains active after receiving a signal.

### Variable Storage
- **`VariableStorageComponent`**: Used to link the electrical activation to specific effects.
    - `name="enable_component"`
    - `value_string="electricity_effect"`: Enables the electrical pulse effect.
    - `value_string="particles_a"`: Enables the first particle emitter.
    - `value_string="particles_b"`: Enables the second particle emitter.

### Lua Scripting
- **`LuaComponent` (Primary)**:
    - `script_electricity_receiver_switched="data/scripts/props/physics_trap.lua"`: The main script handling the trap's behavior when switched on.
- **`LuaComponent` (Electrical Pulse)**:
    - `_tags="electricity_effect"`: Tag to enable this component when electricity is active.
    - `_enabled="0"`: Disabled by default, enabled by `enable_component` variable.
    - `script_source_file="data/scripts/props/physics_trap_electricity_pulse.lua"`: Script responsible for the electrical pulse effect.
    - `execute_every_n_frame="128"`: How often the script logic runs.

### Particle Emitters

#### Sprite Particle Emitter (`particles_a`)
- **`SpriteParticleEmitterComponent`**:
    - `_tags="particles_a"`: Linked to the `enable_component` variable.
    - `_enabled="0"`: Disabled by default.
    - `sprite_file="data/particles/spark_electric.xml"`: The particle effect to emit.
    - `emission_interval_min_frames="128"`: Minimum frames between emissions.
    - `emission_interval_max_frames="128"`: Maximum frames between emissions.
    - `count_min="3"`: Minimum particles per emission.
    - `count_max="10"`: Maximum particles per emission.
    - `randomize_rotation.min="-3.1415"`: Randomizes particle rotation.
    - `randomize_position.min_x="-14"`: Randomizes particle spawn position.

#### Cosmetic Particle Emitter (`particles_b`)
- **`ParticleEmitterComponent`**:
    - `_tags="particles_b"`: Linked to the `enable_component` variable.
    - `_enabled="0"`: Disabled by default.
    - `emitted_material_name="spark_electric"`: The material of the emitted particles.
    - `x_vel_min="-50"`: Minimum horizontal velocity of particles.
    - `y_vel_min="-100"`: Minimum vertical velocity of particles.
    - `count_min="20"`: Minimum particles per emission.
    - `count_max="60"`: Maximum particles per emission.
    - `lifetime_min="0.1"`: Minimum particle lifetime.
    - `lifetime_max="0.75"`: Maximum particle lifetime.
    - `emit_cosmetic_particles="1"`: Emits cosmetic particles.
    - `emission_interval_min_frames="128"`: Minimum frames between emissions.
    - `emission_interval_max_frames="128"`: Maximum frames between emissions.

### Damage and Destruction
- **`DamageModelComponent`**:
    - `hp`: `30` - The health of the trap.
    - `materials_that_damage="fire,lava,acid"`: Materials that can damage the trap.
    - `materials_how_much_damage="0.0002,0.0001,0.001"`: The damage values for the respective materials.
    - `damage_multipliers`:
        - `melee="0.1"`: Reduced damage from melee attacks.
        - `electricity="0"`: Immune to electrical damage.
- **`ExplodeOnDamageComponent`**:
    - `explode_on_death_percent="1"`: The trap will explode when destroyed.
    - `physics_body_destruction_required="0.15"`: The percentage of physics body destruction needed to trigger an explosion.
    - `config_explosion`:
        - `damage`: `2.6` - Damage dealt by the explosion.
        - `camera_shake`: `10` - Intensity of camera shake.
        - `explosion_radius`: `16` - The radius of the explosion.
        - `load_this_entity="data/entities/projectiles/thunderball.xml"`: The entity spawned by the explosion.
        - `ray_energy`: `25000` - Energy of the electrical rays from the explosion.
        - `physics_explosion_power.min="1.7"`: Minimum physics force applied by the explosion.
        - `audio_event_name="explosions/electric"`: The sound effect for the explosion.