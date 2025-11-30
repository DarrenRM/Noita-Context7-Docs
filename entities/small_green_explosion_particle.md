---
title: Small Green Explosion Particle
category: entities
---

# Small Green Explosion Particle

This entity defines a small green explosion effect, composed of several other particle entities.

## Key Components

The primary functionality is driven by `LoadEntitiesComponent`, which spawns other entities when this particle is created.

### `LoadEntitiesComponent`

This component is used multiple times to load different particle effects that make up the overall explosion.

| Attribute      | Description                                                              |
|----------------|--------------------------------------------------------------------------|
| `count.min`    | Minimum number of entities to spawn.                                     |
| `count.max`    | Maximum number of entities to spawn.                                     |
| `kill_entity`  | If `1`, the entity that spawned this particle will be destroyed.         |
| `entity_file`  | The path to the entity file to load.                                     |

### Loaded Entities

The following entities are loaded to create the visual effect:

| `entity_file`                                                              | `count.min` | `count.max` | `kill_entity` | Description                                                              |
|----------------------------------------------------------------------------|-------------|-------------|---------------|--------------------------------------------------------------------------|
| `data/entities/particles/particle_explosion/explosion_flare_small.xml`     | 1           | 1           | 0             | A small, bright flare for the explosion.                                 |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole_small.xml` | 1           | 1           | 0             | Creates a small hole in the fog of war, likely a visual distortion.      |
| `data/entities/particles/particle_explosion/explosion_trail_smoke_green.xml` | 3           | 4           | 0             | Green smoke trails emanating from the explosion.                           |
| `data/entities/particles/particle_explosion/explosion_trail_spark_small.xml` | 2           | 3           | 1             | Small sparks that trail from the explosion, and this component destroys the originating entity. |