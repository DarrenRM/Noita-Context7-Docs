---
title: Spore Pod Spikes Particle
category: entities/particles
---

# Spore Pod Spikes Particle

This entity defines the particle effect for spikes released from a spore pod.

## Key Components

### LoadEntitiesComponent
This component is responsible for spawning other entities.

*   **count.min**: The minimum number of entities to spawn.
    *   Value: `20`
*   **count.max**: The maximum number of entities to spawn.
    *   Value: `20`
*   **kill_entity**: Determines if the parent entity should be killed after spawning.
    *   Value: `0` (False - parent entity is not killed)
*   **entity_file**: The path to the entity file to be spawned.
    *   Value: `data/entities/projectiles/deck/spore_pod_spike.xml`

This configuration indicates that when this particle entity is activated, it will spawn exactly 20 instances of the `spore_pod_spike.xml` projectile entity, and the particle entity itself will persist.