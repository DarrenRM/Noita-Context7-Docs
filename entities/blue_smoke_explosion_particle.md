---
title: Blue Smoke Explosion Particle
category: entities
---

# Blue Smoke Explosion Particle

This entity defines a particle effect that creates a blue smoke explosion. It achieves this by loading several other particle entities.

## Key Components

### LoadEntitiesComponent

This component is responsible for spawning other entities. In this case, it's used to instantiate various smoke and spark particles to form the explosion effect.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `count.min`    | Minimum number of entities to spawn.                                        |
| `count.max`    | Maximum number of entities to spawn.                                        |
| `kill_entity`  | Whether to kill the parent entity after spawning. `0` means no, `1` means yes. |
| `entity_file`  | The path to the entity file to load.                                        |

### Loaded Entities

The following entities are loaded to create the blue smoke explosion:

| Entity File                                                              | Count (min-max) | Kills Parent | Description                                     |
|--------------------------------------------------------------------------|-----------------|--------------|-------------------------------------------------|
| `data/entities/particles/particle_explosion/explosion_flare.xml`         | 1-1             | No           | A general explosion flare particle.             |
| `data/entities/particles/particle_explosion/explosion_flare_fog_of_war_hole.xml` | 1-1             | No           | A flare that creates a fog of war hole.         |
| `data/entities/particles/particle_explosion/explosion_trail_smoke_grey.xml` | 10-12           | No           | Grey smoke trails for the explosion.            |
| `data/entities/particles/particle_explosion/explosion_trail_spark_blue.xml` | 10-12           | Yes          | Blue sparks that trail from the explosion.      |