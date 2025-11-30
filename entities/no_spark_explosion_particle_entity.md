---
title: No Spark Explosion Particle Entity
category: entities
---

# No Spark Explosion Particle Entity

This entity defines a particle effect for an explosion that does not produce sparks. It primarily functions by loading other pre-defined particle entities to create the visual effect.

## Key Components

### LoadEntitiesComponent

This component is responsible for spawning other entities. In this case, it's used to instantiate various explosion-related particle effects.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `count.min`      | Minimum number of entities to spawn.                                        |
| `count.max`      | Maximum number of entities to spawn.                                        |
| `kill_entity`    | If `1`, the entity that spawned this component will be destroyed after execution. |
| `entity_file`    | The path to the entity file to be loaded.                                   |
| `timeout_frames` | (Optional) The number of frames to wait before executing the component.     |

#### Loaded Entities:

| `entity_file`                                                     | `count.min` | `count.max` | `kill_entity` | `timeout_frames` | Notes                                                              |
| :---------------------------------------------------------------- | :---------- | :---------- | :------------ | :--------------- | :----------------------------------------------------------------- |
| `data/entities/particles/particle_explosion/explosion_flare.xml`  | 1           | 1           | 0             | -                | Spawns a basic explosion flare.                                    |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1           | 1           | 0             | -                | Spawns a flare that creates a hole in the fog of war.              |
| `data/entities/particles/particle_explosion/explosion_trail_smoke_nospark.xml` | 10          | 12          | 0             | -                | Spawns multiple smoke trails without sparks.                       |
| `data/entities/particles/particle_explosion/explosion_trail_spark.xml` | 10          | 12          | 0             | -                | Spawns multiple spark trails.                                      |
| `data/entities/particles/particle_explosion/explosion_smoke_pillar.xml` | 1           | 1           | 1             | 3                | Spawns a smoke pillar and then kills the parent entity after 3 frames. |