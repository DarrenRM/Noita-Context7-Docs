---
title: Pink Explosion Particle Entity
category: entities
---

# Pink Explosion Particle Entity

This entity defines a specific type of explosion particle effect, characterized by pink visual elements. It primarily functions by loading other pre-defined particle entities to construct the overall visual.

## Key Components

### LoadEntitiesComponent

This component is responsible for spawning other entities. In this case, it's used to assemble the pink explosion effect from various sub-particle components.

| Attribute      | Description                                                                                             |
|----------------|---------------------------------------------------------------------------------------------------------|
| `count.min`    | The minimum number of entities to spawn.                                                                |
| `count.max`    | The maximum number of entities to spawn.                                                                |
| `kill_entity`  | If set to `1`, the entity that spawned this component will be destroyed after the component finishes. |
| `timeout_frames` | The number of frames to wait before `kill_entity` takes effect (if applicable).                         |
| `entity_file`  | The path to the entity file to load.                                                                    |

### Loaded Entities

The following entities are loaded to create the pink explosion effect:

| Entity File                                                              | Count (min-max) | Notes                                       |
|--------------------------------------------------------------------------|-----------------|---------------------------------------------|
| `data/entities/particles/particle_explosion/explosion_flare.xml`         | 1-1             | Base explosion flare.                       |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1-1             | Creates a fog of war hole effect.           |
| `data/entities/particles/particle_explosion/explosion_trail_smoke_pink.xml` | 10-12           | Pink smoke trails.                          |
| `data/entities/particles/particle_explosion/explosion_trail_spark_pink.xml` | 10-12           | Pink spark trails.                          |
| `data/entities/particles/particle_explosion/explosion_smoke_pillar_pink.xml` | 1-1             | Pink smoke pillar, destroyed after 3 frames. |