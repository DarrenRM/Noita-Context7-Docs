---
title: Gas Pipe Floor
category: entities
---

# Gas Pipe Floor

This entity represents a floor-mounted gas pipe that emits a specific gas. It's a static building element with physics properties and damage handling.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits physics and basic entity properties from a generic physics item.

### Physics Body

*   **`PhysicsBody2Component`**:
    *   `is_static="1"`: The pipe is fixed in place and does not move.
    *   `kill_entity_if_body_destroyed="1"`: The entity will be destroyed if its physics body is destroyed.
    *   `destroy_body_if_entity_destroyed="1"`: The physics body will be destroyed if the entity is destroyed.

### Physics Image Shape

*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/buildings_gfx/drain_pipe_floor.png"`: Specifies the visual sprite for the gas pipe.
    *   `material="steel"`: The material of the pipe, influencing its interaction with other elements.
    *   `centered="1"`: The image is centered on the entity's position.

### Damage Model

*   **`DamageModelComponent`**:
    *   `hp="50"`: The entity's health points.
    *   `falling_damages="0"`: The pipe does not take damage from falling.
    *   `fire_damage_amount="0.4"`: The amount of damage taken from fire.
    *   `materials_that_damage="lava"`: Specifies materials that can damage the pipe.
    *   `materials_how_much_damage="0.0002"`: The rate at which damaging materials inflict damage.
    *   `critical_damage_resistance="1"`: No specific resistance or vulnerability to critical damage.
    *   **`damage_multipliers`**:
        *   `melee="0.1"`: Takes only 10% of normal damage from melee attacks.

### Particle Emitter

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="acid_gas"`: The type of particle (gas) that is emitted.
    *   `x_pos_offset_min="-3"`, `x_pos_offset_max="3"`: Horizontal spread of emitted particles.
    *   `y_pos_offset_min="-7"`, `y_pos_offset_max="-8"`: Vertical spread of emitted particles.
    *   `y_vel_min="0"`, `y_vel_max="50"`: Vertical velocity of emitted particles, causing them to rise.
    *   `count_min="1"`, `count_max="2"`: Number of particles emitted per emission cycle.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="5"`: Controls the frequency of particle emissions.
    *   `is_emitting="1"`: The particle emitter is active.