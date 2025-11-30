---
title: Base Ice Card Visuals
category: entities
---

# Base Ice Card Visuals

This entity defines the visual effects associated with the "Base Ice" card when it's held in the player's hand. It primarily uses particle emitters to create visual flair.

## Key Components

### InheritTransformComponent

This component ensures the visual effects are correctly positioned relative to the player's hand and the "shoot" position.

*   **`_tags`**: `enabled_in_world`, `enabled_in_hand` - The effects are active when the card is in the world or held.
*   **`parent_hotspot_tag`**: `shoot_pos` - Aligns the effects with the weapon's firing point.

### SpriteParticleEmitterComponent

This component emits blue spark particles to represent the "ice" visual.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Active when the item is held and identified.
*   **`sprite_file`**: `data/particles/spark_particle_blue.xml` - Specifies the visual asset for the particles.
*   **`delay`**: `0` - Particles start emitting immediately.
*   **`lifetime`**: `0` - Particles have no inherent lifetime, controlled by other factors.
*   **`color`**: `r="1" g="1" b="1" a="1"` - White color for the sparks.
*   **`gravity`**: `y="-40"` - Particles are affected by gravity, pulling them downwards.
*   **`emission_interval_min_frames`**: `4`
*   **`emission_interval_max_frames`**: `15` - Controls the rate of particle emission.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Emits a single particle per emission cycle.
*   **`randomize_rotation`**: `min="-3.1415" max="3.1415"` - Particles can have random initial rotations.
*   **`randomize_position`**: `min_x="-2" max_x="2" min_y="-2" max_y="2"` - Particles spawn within a small area around the emitter.
*   **`randomize_velocity`**: `min_x="-8" max_x="8" min_y="-24" max_y="8"` - Particles have randomized initial velocities, with a strong downward component.

### ParticleEmitterComponent

This component emits "smoke" particles, likely to add a subtle visual effect or trail.

*   **`_tags`**: `enabled_in_hand`, `item_identified` - Active when the item is held and identified.
*   **`emitted_material_name`**: `smoke` - Specifies the material for these particles.
*   **`offset`**: `x="0" y="0"` - Centered on the emitter.
*   **`x_pos_offset_min`**: `-3`
*   **`x_pos_offset_max`**: `3`
*   **`y_pos_offset_min`**: `1`
*   **`y_pos_offset_max`**: `-1` - Particles spawn in a small horizontal and slightly downward area.
*   **`x_vel_min`**: `-2`
*   **`x_vel_max`**: `2`
*   **`y_vel_min`**: `-20`
*   **`y_vel_max`**: `-10` - Particles have a downward velocity.
*   **`count_min`**: `1`
*   **`count_max`**: `1` - Emits a single particle per emission cycle.
*   **`lifetime_min`**: `0.2`
*   **`lifetime_max`**: `0.3` - Particles have a short lifespan.
*   **`create_real_particles`**: `1` - Creates actual particles in the game world.
*   **`emit_cosmetic_particles`**: `1` - These are purely visual.
*   **`emission_interval_min_frames`**: `5`
*   **`emission_interval_max_frames`**: `12` - Controls the rate of smoke particle emission.
*   **`is_emitting`**: `1` - The emitter is active.