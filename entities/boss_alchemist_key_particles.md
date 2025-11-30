---
title: Boss Alchemist Key Particles
category: entities
---

# Boss Alchemist Key Particles

This entity defines particle effects associated with the Boss Alchemist. It utilizes two `ParticleEmitterComponent` instances to generate different types of particles.

## Key Components

### InheritTransformComponent

This component is present to ensure the entity inherits transformations, likely for positioning and integration within the game world.

*   **_tags**: `first,enabled_in_hand,enabled_in_world,item_identified` - Indicates the entity's state and when it should be active.

### ParticleEmitterComponent (Red Sparks)

This component is responsible for emitting red sparks.

*   **emitted_material_name**: `spark_red` - Specifies the material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles have no vertical gravity.
*   **lifetime_min**: `1.5` - Minimum duration a particle exists.
*   **lifetime_max**: `8.5` - Maximum duration a particle exists.
*   **count_min**: `0` - Minimum particles emitted per emission.
*   **count_max**: `1` - Maximum particles emitted per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **area_circle_radius.max**: `6` - The maximum radius of the circular emission area.
*   **emission_interval_min_frames**: `4` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `30` - Maximum frames between particle emissions.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **collide_with_grid**: `0` - Particles do not collide with the game grid.
*   **cosmetic_force_create**: `1` - Forces the creation of cosmetic particles.
*   **is_emitting**: `1` - The emitter is active.

### ParticleEmitterComponent (White Sparks)

This component is responsible for emitting white sparks.

*   **emitted_material_name**: `spark` - Specifies the material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles have no vertical gravity.
*   **lifetime_min**: `2.5` - Minimum duration a particle exists.
*   **lifetime_max**: `13.5` - Maximum duration a particle exists.
*   **count_min**: `0` - Minimum particles emitted per emission.
*   **count_max**: `1` - Maximum particles emitted per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **area_circle_radius.max**: `16` - The maximum radius of the circular emission area.
*   **emission_interval_min_frames**: `2` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `10` - Maximum frames between particle emissions.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **collide_with_grid**: `0` - Particles do not collide with the game grid.
*   **cosmetic_force_create**: `1` - Forces the creation of cosmetic particles.