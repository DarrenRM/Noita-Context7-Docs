---
title: Large Gunpowder Explosion Particle Effect
category: entities
---

# Large Gunpowder Explosion Particle Effect

This entity defines the particle effects that constitute a large gunpowder explosion in Noita. It primarily uses `LoadEntitiesComponent` to spawn various pre-defined particle entities, creating a layered and dynamic visual effect.

## Key Components

### `LoadEntitiesComponent`

This component is responsible for spawning other entities. The following are the key instances used in this entity:

*   **`explosion_flare.xml`**: Spawns a primary explosion flare.
    *   `count.min`: 1
    *   `count.max`: 1
    *   `kill_entity`: 0 (The spawned entity is not immediately killed)
*   **`explosion_flare_fog_of_war_hole.xml`**: Spawns a flare that creates a temporary hole in the fog of war.
    *   `count.min`: 1
    *   `count.max`: 1
    *   `kill_entity`: 0
*   **`explosion_trail_smoke_gunpowder.xml`**: Spawns trails of gunpowder smoke.
    *   `count.min`: 4
    *   `count.max`: 16
    *   `kill_entity`: 0
*   **`explosion_smoke_gunpowder_large.xml`**: Spawns larger particles of gunpowder smoke.
    *   `count.min`: 12
    *   `count.max`: 24
    *   `kill_entity`: 0
*   **`ember_trail.xml`**: Spawns ember trails, contributing to the fiery aspect of the explosion.
    *   `count.min`: 10
    *   `count.max`: 25
    *   `kill_entity`: 1 (The spawned ember trails are intended to be short-lived and are killed after spawning)

## Summary

The `main_gunpowder_large.xml` entity orchestrates a complex particle explosion by instantiating several other particle effect entities. It focuses on creating a visually impactful explosion with flares, smoke, and embers, with varying counts to ensure a dynamic and less repetitive appearance each time it's triggered. The `kill_entity="1"` on the `ember_trail.xml` suggests these specific particles are designed to be ephemeral.