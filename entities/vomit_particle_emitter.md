---
title: Vomit Particle Emitter
category: entities
---

# Vomit Particle Emitter

This entity defines the behavior and appearance of the "vomit" particle effect in Noita. It's designed to be spawned from a character's hand and creates a stream of vomit particles with specific physical properties and sound effects.

## Key Components

### InheritTransformComponent

This component dictates how the particle emitter's transform is inherited.

*   **parent\_hotspot\_tag**: `hand` - The particles will originate from the "hand" hotspot of the parent entity.
*   **Transform**:
    *   **position.x**: `6` - Offset on the X-axis from the parent's hotspot.
    *   **position.y**: `-5` - Offset on the Y-axis from the parent's hotspot.

### LifetimeComponent

Determines the overall duration of the entity.

*   **lifetime**: `30` - The entity will exist for 30 frames.

### ParticleEmitterComponent

This is the core component responsible for generating and managing the particles.

*   **emitted\_material\_name**: `vomit` - Specifies the material of the particles being emitted.
*   **gravity.y**: `150.0` - The downward force applied to the particles.
*   **lifetime\_min**: `10` - Minimum lifetime of individual particles in frames.
*   **lifetime\_max**: `20` - Maximum lifetime of individual particles in frames.
*   **count\_min**: `1` - Minimum number of particles emitted per emission interval.
*   **count\_max**: `2` - Maximum number of particles emitted per emission interval.
*   **render\_on\_grid**: `1` - Particles will be rendered on the game grid.
*   **cosmetic\_force\_create**: `0` - Particles are not forced to be cosmetic.
*   **airflow\_force**: `0.5` - The strength of airflow affecting the particles.
*   **airflow\_time**: `1.9` - How long airflow affects the particles.
*   **airflow\_scale**: `0.15` - The scaling factor for airflow.
*   **emission\_interval\_min\_frames**: `1` - Minimum frames between particle emissions.
*   **emission\_interval\_max\_frames**: `1` - Maximum frames between particle emissions.
*   **emit\_cosmetic\_particles**: `0` - Cosmetic particles are not emitted.
*   **emit\_real\_particles**: `1` - Real particles are emitted.
*   **x\_vel\_min**: `15` - Minimum initial velocity on the X-axis.
*   **x\_vel\_max**: `20` - Maximum initial velocity on the X-axis.
*   **y\_vel\_min**: `-5` - Minimum initial velocity on the Y-axis.
*   **y\_vel\_max**: `5` - Maximum initial velocity on the Y-axis.
*   **is\_emitting**: `1` - The emitter is active and will emit particles.

### AudioComponent

Handles the sound effects associated with this entity.

*   **file**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound event.
*   **event\_root**: `game_effect/food_poisoning` - The specific sound event to play.