---
title: Physics Trap - Circle Acid
category: entities
---

# Physics Trap - Circle Acid

This entity represents a physics-based trap that, when activated by electricity, can explode and release acid. It's designed to be a hazard that can be triggered by the player or other game elements.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits physics properties and behaviors from a generic physics item.

### Visuals and Physics

*   **`PhysicsImageShapeComponent`**:
    *   `image_file`: `data/props_gfx/trap_acid.png` - Specifies the visual sprite for the trap.
    *   `material`: `steel` - Defines the physical material properties.
    *   `centered`: `1` - Centers the image on the physics body.

### Activation and Behavior

*   **`ElectricityReceiverComponent`**:
    *   `radius`: `6` - The radius within which the trap can receive electrical signals.
    *   `active_time_frames`: `100` - The duration (in frames) the trap remains active after receiving a signal.
*   **`LuaComponent`**:
    *   `script_electricity_receiver_switched`: `data/scripts/props/physics_trap.lua` - Links to a Lua script that handles the trap's behavior when switched on by electricity.

### Variable Storage

*   **`VariableStorageComponent` (entity\_file)**:
    *   `value_string`: `data/entities/projectiles/deck/circle_acid.xml` - Stores the entity file to be loaded upon explosion.
*   **`VariableStorageComponent` (offset\_x)**:
    *   `value_int`: `15` - An offset value, likely used in conjunction with the spawned entity.

### Damage and Health

*   **`DamageModelComponent`**:
    *   `hp`: `30` - The hit points of the trap.
    *   `falling_damages`: `0` - The trap does not take damage from falling.
    *   `materials_that_damage`: `fire,lava,acid` - Specifies materials that can damage the trap.
    *   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage multipliers for the respective materials.
    *   `blood_material`: `acid` - When damaged, it can produce acid.
    *   `damage_multipliers`:
        *   `melee`: `0.1` - Reduced damage from melee attacks.
        *   `electricity`: `0` - Immune to electrical damage.

### Explosion Properties

*   **`ExplodeOnDamageComponent`**:
    *   `explode_on_death_percent`: `1` - The trap will always explode when destroyed.
    *   `physics_body_destruction_required`: `0.15` - The trap needs to be at least 15% destroyed to trigger an explosion.
    *   `physics_body_modified_death_probability`: `0.9` - If the destruction level exceeds `physics_body_destruction_required`, there's a 90% chance it will explode.
    *   **`config_explosion`**:
        *   `damage`: `2.6` - The base damage dealt by the explosion.
        *   `camera_shake`: `10` - The intensity of camera shake upon explosion.
        *   `explosion_radius`: `32` - The radius of the explosion's effect.
        *   `load_this_entity`: `data/entities/projectiles/deck/circle_acid.xml` - The entity to spawn upon explosion (likely an acid projectile).
        *   `damage_mortals`: `1` - The explosion damages living entities.
        *   `physics_explosion_power.min`/`max`: `1.7`/`2.3` - The minimum and maximum force of the physics-based explosion.
        *   `audio_event_name`: `explosions/machine_small` - The sound effect played upon explosion.