---
title: Small Explosion Particle Entity
category: entities
---

# Small Explosion Particle Entity

This entity defines a small explosion effect, primarily composed of various particle effects. It acts as a container for other particle entities that are spawned when this entity is activated.

## Key Components

### LoadEntitiesComponent

This component is responsible for loading and spawning other entities. In this case, it's used to instantiate different types of explosion particles.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `count.min`   | The minimum number of entities to spawn.                                 |
| `count.max`   | The maximum number of entities to spawn.                                 |
| `kill_entity` | Whether to destroy the parent entity after spawning. `0` means no, `1` means yes. |
| `entity_file` | The path to the entity file to load.                                     |

### Spawned Entities

The following entities are spawned by `LoadEntitiesComponent`:

*   **`data/entities/particles/particle_explosion/explosion_flare_small.xml`**: Spawns a small explosion flare.
    *   `count.min="1"`
    *   `count.max="1"`
    *   `kill_entity="0"`
*   **`data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole_small.xml`**: Spawns a small fog of war hole flare.
    *   `count.min="1"`
    *   `count.max="1"`
    *   `kill_entity="0"`
*   **`data/entities/particles/particle_explosion/explosion_trail_smoke.xml`**: Spawns smoke trail particles.
    *   `count.min="5"`
    *   `count.max="8"`
    *   `kill_entity="0"`
*   **`data/entities/particles/particle_explosion/explosion_trail_spark_small.xml`**: Spawns small spark trail particles.
    *   `count.min="3"`
    *   `count.max="4"`
    *   `kill_entity="1"` (This entity will be destroyed after spawning sparks)