---
title: Physics Trap - Electricity Enabled
category: entities
---

# Physics Trap - Electricity Enabled

This entity represents an electrical trap that can be activated by receiving electricity. When activated, it emits sparks and can trigger an explosion upon taking sufficient damage.

## Key Components

### Base Entity

*   **`mortal` tag**: Required for the entity to be able to explode.

### Physics Image Shape Component

Defines the visual representation and physical properties of the trap.

*   **`image_file`**: `data/props_gfx/trap_electricity.png` - The sprite used for the trap.
*   **`material`**: `steel` - The material type, influencing its physical interactions.

### Electricity Receiver Component

Handles the trap's response to electrical input.

*   **`radius`**: `6` - The radius around the trap within which it can receive electrical signals.
*   **`active_time_frames`**: `100` - The duration (in frames) the trap remains active after receiving a signal.

### Lua Component

Executes custom Lua script for the trap's behavior.

*   **`_tags`**: `electricity_effect` - Tags associated with the script's execution.
*   **`script_source_file`**: `data/scripts/props/physics_trap_electricity_pulse.lua` - The path to the Lua script that defines the trap's electrical pulse behavior.
*   **`execute_every_n_frame`**: `128` - The interval (in frames) at which the Lua script is executed.

### Sprite Particle Emitter Component

Responsible for emitting visual spark particles.

*   **`sprite_file`**: `data/particles/spark_electric.xml` - The particle definition for the sparks.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `128` - Controls the timing of particle emissions.
*   **`count_min` / `count_max`**: `3` / `10` - The range of particles emitted per emission.
*   **`randomize_rotation`**: Controls the random rotation of emitted particles.
*   **`randomize_position`**: Controls the random positioning of emitted particles within a defined area.

### Particle Emitter Component

Another particle emitter, likely for more general particle effects.

*   **`emitted_material_name`**: `spark_electric` - The material of the particles to be emitted.
*   **`x_vel_min` / `x_vel_max`**: `-50` / `50` - The range of horizontal velocity for emitted particles.
*   **`y_vel_min` / `y_vel_max`**: `-100` / `50` - The range of vertical velocity for emitted particles.
*   **`count_min` / `count_max`**: `20` / `60` - The range of particles emitted per emission.
*   **`lifetime_min` / `lifetime_max`**: `0.1` / `0.75` - The duration of emitted particles.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `128` - Controls the timing of particle emissions.
*   **`is_emitting`**: `1` - Enables particle emission.

### Damage Model Component

Defines how the trap takes damage and its properties.

*   **`hp`**: `30` - The hit points of the trap.
*   **`materials_that_damage`**: `fire,lava,acid` - Materials that inflict damage to the trap.
*   **`materials_how_much_damage`**: `0.0002,0.0001,0.001` - The damage values for the respective materials.
*   **`damage_multipliers`**:
    *   `melee`: `0.1` - Reduces melee damage taken.
    *   `electricity`: `0` - The trap is immune to direct electrical damage.

### Explode On Damage Component

Manages the trap's explosion behavior when damaged.

*   **`explode_on_death_percent`**: `1` - The trap will always attempt to explode upon death.
*   **`physics_body_destruction_required`**: `0.15` - The threshold of physical destruction required to trigger an explosion.
*   **`physics_body_modified_death_probability`**: `0.9` - If destruction exceeds the threshold, there's a 90% chance it will explode.
*   **`config_explosion`**: Contains detailed settings for the explosion:
    *   **`damage`**: `2.6` - The damage dealt by the explosion.
    *   **`camera_shake`**: `10` - The intensity of camera shake during the explosion.
    *   **`explosion_radius`**: `16` - The radius of the explosion's effect.
    *   **`explosion_sprite`**: `data/particles/explosion_016_electric.xml` - The visual effect for the explosion.
    *   **`load_this_entity`**: `data/entities/projectiles/thunderball.xml` - An entity to spawn upon explosion (e.g., a thunderball projectile).
    *   **`ray_energy`**: `25000` - The energy of the explosion's rays.
    *   **`physics_explosion_power.min` / `physics_explosion_power.max`**: `1.7` / `2.3` - The range of physics force applied by the explosion.
    *   **`audio_event_name`**: `explosions/electric` - The sound effect played during the explosion.