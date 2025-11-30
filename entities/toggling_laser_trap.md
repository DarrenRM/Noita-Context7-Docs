---
title: Toggling Laser Trap
category: entities
---

# Toggling Laser Trap

This entity represents a laser trap that can be toggled on and off, typically by receiving electricity.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.
- `allow_sleep`: Whether the body can go to sleep when inactive.
- `angular_damping`: Resistance to rotational movement.
- `linear_damping`: Resistance to linear movement.

### PhysicsImageShapeComponent
Defines the visual shape and physical material of the trap.
- `image_file`: Path to the sprite used for the trap.
- `material`: The physical material of the trap (e.g., "steel").

### ElectricityReceiverComponent
Enables the entity to react to electrical input.
- `radius`: The radius around the receiver that detects electricity.
- `active_time_frames`: How long the trap remains active after receiving a signal.

### Entity (Laser)
This nested entity defines the laser emitter.
- **LaserEmitterComponent**:
    - `_tags`: Tags associated with the laser, useful for scripting.
    - `is_emitting`: Initial state of the laser (0 for off, 1 for on).
    - **laser**:
        - `max_length`: The maximum distance the laser can travel.
- **InheritTransformComponent**:
    - **Transform**:
        - `position.x`: Offset of the laser emitter relative to the trap's origin.

### LuaComponent (trap_laser_toggle.lua)
This component executes a Lua script for the trap's toggling logic.
- `script_source_file`: Path to the Lua script.
- `execute_every_n_frame`: How often the script is executed.

### LuaComponent (trap_laser_init.lua)
This component executes a Lua script once on entity creation for initialization.
- `script_source_file`: Path to the Lua script.
- `execute_on_added`: Ensures the script runs when the entity is added.
- `remove_after_executed`: Removes this component after its script has run.

### VariableStorageComponent
Stores variables for the entity.
- `name`: The name of the variable (e.g., "status").
- `value_int`: The initial integer value of the variable.

### SpriteComponent
Defines the visual overlay for the laser trap.
- `_tags`: Tags associated with the sprite.
- `_enabled`: Whether the sprite is initially enabled.
- `image_file`: Path to the sprite's image file.
- `rect_animation`: Specifies the rectangle animation to use.
- `z_index`: Controls the drawing order of the sprite.

### DamageModelComponent
Manages how the entity takes damage and its health.
- `hp`: The entity's hit points.
- `falling_damage_damage_max`/`min`: Maximum and minimum damage from falling.
- `fire_damage_amount`: Amount of damage taken from fire.
- `materials_that_damage`: List of materials that damage this entity.
- `materials_how_much_damage`: Corresponding damage values for each material.
- **damage_multipliers**:
    - `melee`: Multiplier for melee damage taken.
    - `electricity`: Multiplier for electricity damage taken.

### ExplodeOnDamageComponent
Defines the explosion behavior when the entity is damaged or destroyed.
- `explode_on_death_percent`: Probability of exploding upon death.
- `physics_body_destruction_required`: Threshold for physics body destruction to trigger explosion.
- **config_explosion**:
    - `damage`: Damage dealt by the explosion.
    - `camera_shake`: Amount of camera shake caused by the explosion.
    - `explosion_radius`: The radius of the explosion.
    - `explosion_sprite`: Path to the particle effect for the explosion.
    - `load_this_entity`: Entity to spawn upon explosion (e.g., a projectile).
    - `audio_event_name`: The sound event to play for the explosion.