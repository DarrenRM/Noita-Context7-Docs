---
title: Small Blue Smoke Explosion Particle
category: entities
---

# Small Blue Smoke Explosion Particle

This entity defines a small blue smoke explosion effect, composed of several other particle entities.

## Key Components

The primary functionality is driven by `LoadEntitiesComponent`, which spawns other entities at the location of this particle.

### LoadEntitiesComponent

This component is responsible for instantiating other entities.

| Attribute      | Description                                                              |
| -------------- | ------------------------------------------------------------------------ |
| `count.min`    | Minimum number of entities to spawn.                                     |
| `count.max`    | Maximum number of entities to spawn.                                     |
| `kill_entity`  | If `1`, the entity that spawned this particle will be destroyed.         |
| `entity_file`  | The path to the entity file to be loaded.                                |

### Spawned Entities

The following entities are spawned by this particle:

| Entity File                                                              | Count (min-max) | Kill Parent | Description                                     |
| ------------------------------------------------------------------------ | --------------- | ----------- | ----------------------------------------------- |
| `data/entities/particles/particle_explosion/explosion_flare_blue_small.xml` | 1-1             | 0           | A small blue flare effect.                      |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole_small.xml` | 1-1             | 0           | Creates a small hole in the fog of war.         |
| `data/entities/particles/particle_explosion/explosion_trail_smoke_grey.xml` | 2-3             | 0           | Grey smoke trails.                              |
| `data/entities/particles/particle_explosion/explosion_trail_spark_blue_small.xml` | 3-4             | 1           | Small blue sparks, and kills the parent entity. |