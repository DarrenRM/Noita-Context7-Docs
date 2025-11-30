---
title: Gas Pipe
category: entities
---

---

# Gas Pipe

This entity represents a gas pipe, a static building that emits a specific material.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits physics properties from a base item.
    *   **`PhysicsBody2Component`**:
        *   `is_static="1"`: The pipe is fixed in place.
        *   `kill_entity_if_body_destroyed="1"`: The entity is destroyed if its physics body is destroyed.
        *   `destroy_body_if_entity_destroyed="1"`: The physics body is destroyed if the entity is destroyed.
    *   **`PhysicsImageShapeComponent`**:
        *   `image_file="data/buildings_gfx/drain_pipe.png"`: Specifies the visual sprite for the pipe.
        *   `material="steel"`: The material of the pipe's collision shape.
        *   `centered="1"`: The image is centered on the entity's position.

### Damage Model

*   **`DamageModelComponent`**: Defines how the pipe takes damage and its properties.
    *   `hp="50"`: The pipe has 50 hit points.
    *   `falling_damages="0"`: The pipe does not take damage from falling.
    *   `fire_damage_amount="0.4"`: Deals 0.4 damage per frame when on fire.
    *   `fire_probability_of_ignition="0"`: Cannot be ignited by fire.
    *   `materials_damage="1"`: Can be damaged by certain materials.
    *   `materials_that_damage="lava"`: Lava is the only material that damages it.
    *   `materials_how_much_damage="0.0002"`: Lava deals 0.0002 damage per frame.
    *   `critical_damage_resistance="1"`: No resistance to critical damage.
    *   `damage_multipliers`:
        *   `melee="0.1"`: Takes only 10% of melee damage.

### Particle Emitter

*   **`ParticleEmitterComponent`**: Controls the emission of particles from the pipe.
    *   `emitted_material_name="acid_gas"`: The pipe emits "acid_gas".
    *   `emission_interval_min_frames="1"`: Particles are emitted every 1 frame.
    *   `emission_interval_max_frames="1"`: Particles are emitted every 1 frame.
    *   `is_emitting="1"`: The emitter is active.
    *   `count_min="1"`: Emits at least 1 particle per emission.
    *   `count_max="2"`: Emits at most 2 particles per emission.
    *   `y_vel_min="0"`: Particles have no initial upward velocity.
    *   `y_vel_max="50"`: Particles have an initial upward velocity up to 50.
    *   `x_pos_offset_min="-4"`: Particles can spawn up to 4 units to the left of the pipe's center.
    *   `x_pos_offset_max="4"`: Particles can spawn up to 4 units to the right of the pipe's center.
    *   `y_pos_offset_min="7"`: Particles can spawn up to 7 units above the pipe's center.
    *   `y_pos_offset_max="11"`: Particles can spawn up to 11 units above the pipe's center.