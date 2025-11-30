---
title: Blue Tiny Explosion Particle
category: entities
---

# Blue Tiny Explosion Particle

This entity defines a small, blue explosion effect composed of several other particle entities. It's primarily used for visual flair in various in-game events.

## Key Components

The `Entity` contains multiple `LoadEntitiesComponent` instances, each responsible for spawning a specific particle effect.

### LoadEntitiesComponent

This component is used to load and spawn other entities.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `count.min`   | Minimum number of entities to spawn.                                     |
| `count.max`   | Maximum number of entities to spawn.                                     |
| `kill_entity` | Whether to destroy the parent entity after spawning. `1` means destroy. |
| `entity_file` | The path to the entity file to be loaded and spawned.                    |

### Spawned Entities

The following particle entities are spawned by this `main_blue_tiny.xml`:

*   **`data/entities/particles/particle_explosion/explosion_flare_blue.xml`**: Spawns a blue flare effect.
*   **`data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml`**: Spawns a fog of war hole flare effect.
*   **`data/entities/particles/particle_explosion/explosion_trail_spark_blue_small.xml`**: Spawns small blue spark trail effects. This is spawned between 1 and 3 times, and the parent entity is destroyed afterward.