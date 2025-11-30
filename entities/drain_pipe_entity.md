---
title: Drain Pipe Entity
category: entities
---

---

# Drain Pipe Entity

This document describes the `drain_pipe.xml` entity, which functions as a biome modifier in Noita. It's a static building entity that can be damaged and destroyed.

## Key Components and Attributes

### Base Entity (`<Base>`)

This section defines the fundamental properties of the drain pipe as a physical object.

*   **`file="data/entities/base_item_physics2.xml"`**: Inherits physics properties from a base physics entity.
*   **`PhysicsBody2Component`**:
    *   `is_static="1"`: The drain pipe is a fixed, immovable object.
    *   `kill_entity_if_body_destroyed="1"`: The entity is destroyed if its physics body is destroyed.
    *   `destroy_body_if_entity_destroyed="1"`: The physics body is destroyed if the entity is destroyed.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/buildings_gfx/drain_pipe.png"`: Specifies the visual sprite for the drain pipe.
    *   `material="steel"`: The material of the drain pipe, influencing its interaction with other elements.
    *   `centered="1"`: The image is centered on the entity's position.

### Damage Model (`<DamageModelComponent>`)

This component governs how the drain pipe takes damage and its resistance to various damage types.

*   **`hp="50"`**: The drain pipe has 50 hit points.
*   **`materials_that_damage="lava,acid"`**: Lava and acid are the primary materials that damage the drain pipe.
*   **`materials_how_much_damage="0.0002,0.0001,0.001"`**: Defines the damage values for the materials that damage it.
*   **`falling_damages="0"`**: The drain pipe does not take damage from falling.
*   **`fire_damage_amount="0.4"`**: It takes a small amount of damage from fire.
*   **`critical_damage_resistance="1"`**: No special resistance to critical damage.
*   **`damage_multipliers`**:
    *   `melee="0.1"`: Takes significantly reduced damage from melee attacks.

### Particle Emitter (`<ParticleEmitterComponent>`)

This component controls the emission of particles, simulating water flowing from the drain pipe.

*   **`emitted_material_name="water"`**: The particles emitted are of the "water" material.
*   **`offset.x="0"`, `offset.y="0"`**: The emission originates from the center of the entity.
*   **`x_pos_offset_min="-3"`, `x_pos_offset_max="3"`**: Small horizontal variation in particle spawn position.
*   **`y_pos_offset_min="7"`, `y_pos_offset_max="8"`**: Particles are spawned slightly above the entity.
*   **`count_min="1"`, `count_max="2"`**: Emits 1 to 2 particles per emission cycle.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="10"`**: Particles are emitted frequently, with a slight random delay between emissions.
*   **`is_emitting="1"`**: The particle emitter is active.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.