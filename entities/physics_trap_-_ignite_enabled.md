---
title: Physics Trap - Ignite Enabled
category: entities
---

---

# Physics Trap - Ignite Enabled

This entity represents a physics-based trap that ignites when damaged or destroyed. It's designed to be a hazard that can be triggered by the player or environmental effects.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics.xml"`**: Inherits core physics properties and behaviors from the base physics item.
    *   **`PhysicsImageShapeComponent`**: Defines the visual representation and physical properties.
        *   `image_file`: `data/props_gfx/trap_ignite_a.png` - The sprite used for the trap.
        *   `material`: `steel` - The material of the trap, influencing its interaction with other physics objects.

### Lua Component

*   **`LuaComponent`**: Attaches a Lua script to control custom behavior.
    *   `script_source_file`: `data/scripts/props/physics_trap_ignite.lua` - The script that handles the trap's ignition logic.
    *   `execute_every_n_frame`: `160` - The script's logic runs periodically.
    *   `_tags="electricity_effect"`: Indicates it can be affected by or interact with electricity.

### Particle Emitters

This entity utilizes multiple `ParticleEmitterComponent`s to create visual and environmental effects upon activation.

*   **Fire Emitter**:
    *   `emitted_material_name`: `fire` - Emits fire particles.
    *   `lifetime_min`/`max`: `15`/`35` frames - Duration of fire particles.
    *   `count_min`/`max`: `100`/`100` - Number of fire particles emitted.
    *   `area_circle_radius.min`/`max`: `12`/`12` - The radius of the emission area.
    *   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Triggers emission periodically.

*   **Alcohol Gas Emitter**:
    *   `emitted_material_name`: `alcohol_gas` - Emits alcohol gas particles.
    *   `lifetime_min`/`max`: `15`/`35` frames - Duration of gas particles.
    *   `count_min`/`max`: `500`/`500` - Number of gas particles emitted.
    *   `area_circle_radius.min`/`max`: `10`/`25` - The radius of the emission area.
    *   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Triggers emission periodically.

*   **Explosion Sprite Emitter**:
    *   `sprite_file`: `data/particles/explosion_032.xml` - Uses a specific sprite for explosion effects.
    *   `emission_interval_min_frames`/`max_frames`: `160`/`160` - Triggers the explosion sprite periodically.

### Damage Model

*   **`DamageModelComponent`**: Defines how the entity takes damage and its reactions.
    *   `hp`: `30` - The entity's health points.
    *   `materials_that_damage`: `fire,lava,acid` - Materials that can damage this entity.
    *   `materials_how_much_damage`: `0.0002,0.0001,0.001` - The damage values for each material.
    *   `falling_damages`: `0` - Does not take damage from falling.
    *   `fire_damage_amount`: `0.4` - The amount of fire damage it deals if it ignites.
    *   `blood_material`: `alcohol_gas` - What material is produced when damaged (used for effects).
    *   `damage_multipliers`:
        *   `melee`: `0.1` - Reduced damage from melee attacks.
        *   `electricity`: `0` - Immune to electricity damage.

### Explode on Damage

*   **`ExplodeOnDamageComponent`**: Controls the entity's explosion behavior.
    *   `explode_on_death_percent`: `1` - Will explode when its health reaches 0.
    *   `physics_body_destruction_required`: `0.15` - The entity's physics body needs to be at least 15% destroyed for potential explosion.
    *   `physics_body_modified_death_probability`: `0.9` - If the destruction threshold is met upon death, there's a 90% chance it will explode.
    *   **`config_explosion`**: Details of the explosion effect.
        *   `damage`: `2.6` - The damage dealt by the explosion.
        *   `camera_shake`: `10` - The intensity of camera shake during the explosion.
        *   `explosion_radius`: `32` - The radius of the explosion's effect.
        *   `load_this_entity`: `data/entities/projectiles/deck/mist_alcohol.xml` - Spawns this entity upon explosion.
        *   `physics_explosion_power.min`/`max`: `1.7`/`2.3` - The force of the physics-based explosion.
        *   `delay.min`/`max`: `1`/`4` - The explosion can have a slight delay.