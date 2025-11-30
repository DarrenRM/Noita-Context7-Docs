---
title: Acid Trap Circle Prop
category: data
---

# Acid Trap Circle Prop

This document details the `trap_circle_acid.xml` entity, a physics-based prop that functions as an acid trap. When activated by electricity, it can trigger an explosion that spawns acid projectiles.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the trap.

*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive.
*   `angular_damping`: `0` - No resistance to rotational movement.
*   `linear_damping`: `0` - No resistance to linear movement.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape.

*   `is_root`: `1` - This component is the root of the entity's visual representation.
*   `centered`: `1` - The image is centered on the entity's origin.
*   `image_file`: `data/props_gfx/trap_acid.png` - The sprite used for the trap.
*   `material`: `steel` - The material type for physics interactions.

### ElectricityReceiverComponent
Enables the trap to react to electrical input.

*   `radius`: `6` - The radius around the trap that can receive electrical signals.
*   `active_time_frames`: `100` - The duration (in frames) the trap remains active after receiving a signal.

### VariableStorageComponent
Stores custom variables for the entity.

*   `name="entity_file"`, `value_string="data/entities/projectiles/deck/circle_acid.xml"`: Specifies the entity to spawn when the trap explodes.
*   `name="offset_x"`, `value_int="15"`: An offset value, likely used in conjunction with spawning projectiles.

### LuaComponent
Links the entity to a Lua script for custom behavior.

*   `script_electricity_receiver_switched`: `data/scripts/props/physics_trap.lua` - The script that handles the trap's behavior when switched by electricity.

### DamageModelComponent
Defines how the trap takes damage and its health.

*   `hp`: `30` - The hit points of the trap.
*   `blood_material`: `acid` - The material that is produced when the trap takes damage (though `materials_create_messages` is `0`).
*   `materials_that_damage`: `fire,lava,acid` - Materials that can damage the trap.
*   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage multipliers for the respective materials.
*   `falling_damage_damage_max`: `1.2` - Maximum damage from falling.
*   `falling_damage_height_max`: `250` - Height at which maximum falling damage is applied.
*   `damage_multipliers`:
    *   `melee`: `0.1` - Reduced damage from melee attacks.
    *   `electricity`: `0` - Immune to electrical damage.

### ExplodeOnDamageComponent
Handles the explosion behavior when the trap is damaged.

*   `explode_on_death_percent`: `1` - The trap will always explode upon death.
*   `physics_body_destruction_required`: `0.15` - The trap's physics body must be at least 15% destroyed for an explosion.
*   `config_explosion`: Contains detailed parameters for the explosion.
    *   `damage`: `2.6` - The base damage of the explosion.
    *   `camera_shake`: `10` - The intensity of camera shake during the explosion.
    *   `explosion_radius`: `32` - The radius of the explosion effect.
    *   `load_this_entity`: `data/entities/projectiles/deck/circle_acid.xml` - The entity to spawn upon explosion.
    *   `damage_mortals`: `1` - The explosion damages living entities.
    *   `physics_explosion_power.min`: `1.7` - Minimum physics force applied by the explosion.
    *   `physics_explosion_power.max`: `2.3` - Maximum physics force applied by the explosion.
    *   `audio_event_name`: `explosions/machine_small` - The sound effect played during the explosion.